Welcome! 

This document is intended for **future developers** who may continue work on the ICN Navigator project. It provides a concise technical overview of the system architecture, file structure, and design decisions made by **Team ZAMJO** during development.  Our goal is to help you quickly understand how the project is organised and how to build upon it effectively.
## Design

Our team used **Figma** for all frontend high fidelity design work. The design file can be accessed [here](https://www.figma.com/design/xqEyJoHTrpyX5ZSwdU9kgM/ICN-Draft-3?node-id=43-239&t=aBIrYXSiqMTxgmXZ-1).

> [!NOTE] Migration
> 
> The free version of Figma limits visibility to three shared pages. Some design pages may therefore be hidden.  
> 
> To view or modify the full project, we recommend [duplicating the file](https://help.figma.com/hc/en-us/articles/360038511533-Duplicate-or-copy-files) into your own workspace.  For ongoing or multi-team development, consider upgrading to a [Team plan](https://help.figma.com/hc/en-us/articles/360040328273-Figma-plans-and-features) to enable proper collaboration and file management.
> 

While detailed design documentation can be found in [[Design Process]], [[Low Fidelity]], and [[High Fidelity]], the following section provides a concise overview specifically aimed at helping future developers understand the design foundations and continue development smoothly.

## Development

### High Level Architecture

For a **high-level understanding** of our system architecture see the diagram below. 

* **Frontend:** We're using *React Native* with the *Expo Framework* (in *Typescript*).
* **Backend:** We're using the *Bun* runtime and framework (with *Typescript*).
* **Database** Our main database is *PostgreSQL*.
* **Hosting:** We are using *Render*'s hosting platform. 

For more details and justification of certain decisions see our architecture [[High Level Overview]]. 

![[high-level-system-arch.svg]]

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
> Zod is a TypeScript-first validation library that we're using to enforce consistent data validation and type safety across the frontend and backend. See the [Zod documentation](https://zod.dev/) to learn more. 

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

We're using MapBox




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
│   ├── notifications/         # Push notifications
│   ├── index.ts               # API server entry point
│   ├── utils.ts               # Shared utility functions
│   └── test-setup.ts          # Test configuration and helpers
│
├── database/                  # Database configuration
│   └── schema.sql             # PostgreSQL schema definition
│
├── scripts/                   # Utility scripts
├── package.json               # Backend dependencies (Bun, Hono)
├── tsconfig.json              # TypeScript configuration
└── README.md                  # API documentation
```

#### Future Development 

#TODO

### Database

The database has the following schema. 

![[ICN Navigator DB Schema.pdf]]

#### Database Access

#TODO Provide comprehensive details on accessing the database, including necessary credentials and an overview of the data schema.

## Hosting Service Access

#TODO Include instructions and credentials for accessing the hosting service where the application is deployed.

## Deployment

#TODO (i.e. how to deploy the source code, database and run the project on a new server, any necessary administrator/test customer login credentials, access to code repositories, databases and servers as well