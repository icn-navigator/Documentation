**Welcome!** 

This document is intended for **future developers** who may continue work on the ICN Navigator project. It provides a concise technical overview of the system architecture, file structure, and design decisions made by **Team ZAMJO** during development.  Our goal is to help you quickly understand how the project is organised and how to build upon it effectively.
## Design

Our team used **Figma** for all frontend high fidelity design work. The design file can be accessed [here](https://www.figma.com/design/xqEyJoHTrpyX5ZSwdU9kgM/ICN-Draft-3?node-id=43-239&t=aBIrYXSiqMTxgmXZ-1).

> [!NOTE] Migration
> 
> The free version of Figma limits visibility to three shared pages. Some design pages may therefore be hidden.  
> 
> To view or modify the full project, we recommend [duplicating the file](https://help.figma.com/hc/en-us/articles/360038511533-Duplicate-or-copy-files) into your own workspace.  For ongoing or multi-team development, consider upgrading to a [Team plan](https://help.figma.com/hc/en-us/articles/360040328273-Figma-plans-and-features) to enable proper collaboration and file management.
> 

Detailed design documentation can be found in [[Design Process]], [[Low Fidelity]], and [[High Fidelity]]. 

## Development

### High Level Architecture

For a **high-level understanding** of our system architecture see the diagram below. 

For more details and justification of certain decisions see our architecture [[High Level Overview]]. 

![[new-high-lvl-sys-arch.png]]

**Note:** This information is slightly outdated, as our hosting provider has since been changed to **Render**.  Hosting is covered in more detail in the [[#Deployment]] section. 
### High-Level File Structure

The project uses a **single monorepo** containing both the frontend and backend. This setup simplifies dependency management and enables shared types between the two environments.

```
ICN-Navigator/
├── frontend/             # React Native app (Expo Router)
├── api/                  # Bun-based REST API backend
├── shared-types/         # Zod schemas shared across frontend/backend
└── README.md             # Project setup and dev instructions
```

> [!INFO]- Shared types
> The `shared-types` directory contains **Zod schemas and TypeScript definitions** used by both the frontend and backend.  
>
> Zod is a TypeScript-first validation library that we're using to enforce consistent data validation and type safety across the frontend and backend. See the [Zod documentation](https://zod.dev/) for examples and best practices.

### Frontend

We're using [React Native](https://reactnative.dev/docs/getting-started) with the [Expo Framework](https://docs.expo.dev/) (in *Typescript*).
#### File Structure

Below is a high-level overview of the **frontend** structure. It follows common React Native and Expo conventions, using **file-based routing** via [Expo Router](https://docs.expo.dev/router/introduction/).

```
frontend/
├── app/                 # File-based routing (Expo Router)
│   ├── (app)/           # Protected app screens (main app)
│   ├── (auth)/          # Authentication screens (login, signup)
│   └── _layout.tsx      # Root layout and navigation structure
│
├── components/          # Reusable UI components
├── hooks/               # Custom React hooks
├── utils/               # Utility functions and helpers
├── config/              # App configuration files
├── constants/           # App-wide constants
├── data/                # Static data files
│
├── assets/              # Static assets (images/fonts/styles)
│
├── package.json         # Frontend dependencies
└── tsconfig.json        # TypeScript configuration
```

#### Map Framework - MapBox

The ICN Navigator frontend uses **Mapbox** via the [`@rnmapbox/maps`](https://github.com/rnmapbox/maps) library to power the interactive map view. For more info and justification of this choice see [[DR07 - Map Framework]]. 

**Configuration:** The Mapbox access token is required to load files - see the main `README.md` for setup instructions.

#### Future Development

The current structure was designed for **clarity, scalability, and maintainability**.  

Future developers should:
- Add new screens within the `app/`, following Expo Router conventions.
- Keep reusable UI components in `components/` and shared logic in `hooks/`

### API / Backend

We're using the [Bun](https://bun.com/docs) runtime and framework (with *Typescript*). For more info Bun and why we chose it see [[DR05 - Backend Language]].

#### File Structure

```
api/
├── src/                       # API source code
│   ├── account/               # User account management endpoints
│   ├── session/               # Authentication and session handling
│   ├── organisations/         # Organization and search
│   ├── items/                 # Items/resources management
│   ├── sectors/               # Industry sectors endpoints
│   ├── subscription/          # Premium subscription logic
│   ├── notifications/         # Notifcations (like email verify)
│   ├── index.ts               # API server entry point
│   └── utils.ts               # Shared utility functions
│
├── database/                  # Database configuration
│   └── schema.sql             # PostgreSQL schema definition
│
├── scripts/                   # Utility scripts
├── package.json               # Backend dependencies (Bun)
├── tsconfig.json              # TypeScript configuration
└── README.md                  # API documentation
```

#### API Documentation

It provides details on all available **endpoints**, including request/response formats, expected parameters, and error codes.  

The documentation was written to help developers integrate with the backend and understand how data flows between the frontend and database.

### Database

The backend uses a [PostgreSQL](https://www.postgresql.org/) database to store information about organisations, capabilities, sections and user accounts. 

An overview of the schema is shown below:

![[ICN Navigator DB Schema.pdf]]

For detailed entity descriptions, relationships, and rationale, see [[Database Overview]].

> [!INFO] Bun and SQL databases
> We take advantage of the native bindings **Bun** provides for working with SQL databases through a unified Promise-based API that supports PostgreSQL, MySQL, and SQLite. (See [here](https://bun.sh/docs/runtime/sql))
#### Database Access

Currently we're using Render's built-in Postgres instance hosting for convenience during testing, however our system is completely provider-agnostic for Postgres instances.

At the top level of the repo is a directory `/icn_data_processing`, which contains the sample data provided as well as *2 Python scripts* for processing it.

>[!Warning] Important Note
> Running the main processing script (`icn_data_analysis.py`) can take up to *6 hours* due to the limited throughput of geocoding the organisation addresses.

Much of this data should already be processed however, so you can run the script `final.py` to produce the output `.csv` files which can be directly imported into a Postgres database.

>[!Info] Note
> `final.py` currently assumes the user is on a MacOS system by default as it saves the output files to the shared directory `/Users/shared/tmp`, which enable a Postgres client like PgAdmin to access the data.
> 
> This can be changed in the script depending on what operating system you have access to.


After processing the data, the file `commands.txt` contains *4 psql commands* that can be run 1-by-1 to insert the data into the connected instance.

#### Future Development

* **Data expansion:** If the data becomes available, consider adding additional organisation attributes such as **diversity filters** or other classification fields.  See also [[tiered-features.pdf]] for further context here.
* **Migrations:** Introduce a structured migration process to safely manage schema changes over time.

## Testing

We have an automated testing suite configured for the backend, which can be run with the command `bun test` from the `api/` directory


## Deployment

As our deployment systems are entirely built around GitHub actions (and hosting platform-specific actions triggered by GitHub commits to `main`), configuring deployment primarily involves getting administrative access to the ICN Navigator GitHub organisation.

Once access to the organisation (and ICN-Navigator repo) are obtained, the rest of the deployment can be configured on the hosting provider *Render*.

### Connecting Repo to Render

While developing, we chose to log into Render with GitHub, as this provides an immediate easy way to access your repositories, and we suggest doing this too.

After logging in, you can create a new *web service* based on a repository, for which you should select the `ICN-Navigator` repo.

>[!Info]
>Here's Render's official documentation on web services, which contains a setup guide: https://render.com/docs/web-services


### Configuring the Render web service

There are a few important configuration changes to make before you can launch the instance.

#### Environment Variables

Environment variables can be configured in Render's environment tab in the dashboard.


A total of 5 environment variables need to be set for the instance to deploy successfully.
- `BUN_VERSION`=1.2.22
- `PORT`=8000
- `EXPO_PUBLIC_MAPBOX_TOKEN`=pk.eyJ1IjoibWF0dGhld3l3IiwiYSI6ImNtZm90dHpqbzBhYzIybnB4bjk4N3VwdXcifQ.1UxsyfBs0eMcPSjEF4lBcA
- `RNMAPBOX_MAPS_DOWNLOAD_TOKEN` *this is private and can be obtained for free by creating a MapBox account*
	- See: https://account.mapbox.com/auth/signup/
- `DATABASE_URL` *this is private and depends on your postgres instance*



#### Build and Start Commands

The commands also need to be configured in the settings tab.
- Build command = `source build.sh`
- Start command = `source start.sh`


The instance should now be ready to deploy.

