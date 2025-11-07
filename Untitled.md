# ICN - Navigator

ICN Navigator is a prototype platform for browsing organisations and their capabilities across Victoria. It provides a map-based interface and filtering tools to explore organisations by sector, region, capabilities and more.

This application was developed as part of [COMP30022 – IT Project](https://handbook.unimelb.edu.au/subjects/comp30022) by Team ZAMJO for our client, [ICN Victoria.](https://icn.org.au/icn_vic/)

## Documentation

Documentation, including developer documentation, is available online here: https://icn-navigator.github.io/Documentation/

**API Documentation:** [link](https://icn-navigator.github.io/Documentation/Developer-Docs/Backend/API-Documentation)

**Git Contribution Guideline**: [link](https://icn-navigator.github.io/Documentation/Standards/Git-Contribution-Guidelines)

## Get started

1. Run the backend

   ```bash
   cd api
   bun install
   bun start
   ```

2. Run the shared types

   ```bash
   cd shared-types
   npm install
   ```

3. Run the frontend

   ```bash
   cd frontend
   npm install

   # Create .env file and add your Mapbox tokens
   cp .env.example .env
   # Edit .env and add both tokens:
   # - EXPO_PUBLIC_MAPBOX_TOKEN (public token for app runtime)
   # - RNMAPBOX_MAPS_DOWNLOAD_TOKEN (secret token for downloading SDK)

   npx expo prebuild --clean     # Generates ios/ and android/ folders
   npx expo run:ios              # Builds and installs the app (takes a while)
   npx expo start --dev-client   # Normal development
   ```

   **When to run each command:**
   - `npx expo prebuild --clean` - if changing packages with native code
   - `npx expo run:ios` - if native code changes or if you delete the app
   - `npx expo start --dev-client` - for normal development. Enables hot-reload

   **Other notes:**
   - Temporary issue: if building the app fails, there may be a trailing comma
   in your `frontend/node_modules/fix/package.json` that should be removed.

4. Configure the webapp

   **- Using expo prebuild, for development**

   ```bash
   npx expo prebuild --clean
   npx expo start --dev-client
   ```

   **- Static site**

    ```bash
   cd frontend
   npx expo export --platform web
   cd ..
   cd api
   bun run start
   ```

   **Other notes:**
   
   - Issue: if Mapbox build fails try

   ```bash
   npm install mapbox-gl
   ```
