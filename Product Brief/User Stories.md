## Platform Access

### US01 - Web Application Access

**As a** user,
**I want to** access the platform through a web browser,
**so that** I can use the service on any desktop or laptop computer without installing software.
**Acceptance Criteria:**
- Application is fully functional in modern web browsers (Chrome, Firefox, Safari, Edge)
- Responsive design adapts to different screen sizes
- All core features are accessible via web interface
- Session persistence across browser sessions

### US02 - Mobile Application Access

**As a** user,
**I want to** access the platform through native mobile apps on iOS and Android,
**so that** I can use the service on-the-go from my smartphone or tablet.
**Acceptance Criteria:**
- Native apps available for iOS and Android devices
- Mobile-optimised UI for touch interactions
- All core features accessible on mobile (with appropriate adaptations for smaller screens)
- Account synchronisation between web and mobile platforms

## Authentication & Onboarding

### US03 - Welcome Page(s)

**As a** new user,
**I want to** see onboarding screens with features and personalisation questions
**so that** I understand what the platform offers.
**Acceptance Criteria**
- A visually appealing welcome screen appears on first visit
- Clearly states the platform's purpose and benefits
- Works properly on both desktop and mobile

### US04 - Account Signup & Login

**As a** visitor,
**I want to** create an account and log in securely,
**so that** I can save my preferences and access more features.
**Acceptance Criteria:**
- Users can create accounts with required fields(Only email for now)

### US05 - Onboarding Questions

**As a** new user,
**I want to** complete onboarding questions about my role, industry, and interests,
**so that** the platform can better understand my needs and provide personalized recommendations.
**Acceptance Criteria:**
- Onboarding questionnaire appears after account creation
- Questions cover user role, industry sector, and company interests
- Users can skip or complete the questions
- Responses are stored for analytics and personalization purposes

### US06 - Subscription Tiers & Feature Access

**As a** user,
**I want to** access different levels of company information and features based on my subscription tier (Free, Plus, Premium),
**so that** I can choose the level of service that meets my needs and budget.
**Acceptance Criteria:**
- Users can view their current subscription tier
- Features are clearly labeled or indicated by tier level
- Premium/Plus features are locked or show upgrade prompts for lower-tier users
- Subscription tier system is modular and configurable to allow features to be moved between tiers
- Users can upgrade their subscription tier from within the app

## Map & Navigation

### US07 - Map View

**As a** user,
**I want to** view companies on a map,
**so that** I can visually explore local businesses and their capabilities.
**Acceptance Criteria:**
- Map displays relevant company pins
- Interactive zoom and pan functions
- Pins load dynamically based on viewport

### US08 - Category Icons

**As a** user,
**I want to** see company locations with category specific icons on the map,
**so that** I can quickly distinguish different types of companies at a glance.
**Acceptance Criteria:**
- Each business category has a meaningful icon
- Icons display properly at various zoom levels
- Tooltip or label appears on hover or click

### US09 - Optional List View

**As a** user,
**I want to** switch between map view and list view,
**so that** I can choose the format that best fits my browsing needs.
**Acceptance Criteria:**
- Toggle button is clearly visible and functional
- Map and List views are synchronized
- Both views have consistent styling and data

## Search & Filtering

### US10 - Searching

**As a** user,
**I want to** search by location or keyword,
**so that** I can quickly find businesses matching specific terms or regions.
**Acceptance Criteria:**
- Search bar accepts location or keyword input
- Autocomplete suggestions appear
- Results are reflected in both map and list view

### US11 - Filtering

**As a** user,
**I want to** filter companies by sector, components, size, capability type, ownership status etc.,
**so that** I can narrow down the most relevant businesses.
**Acceptance Criteria:**
- Filters include sector, components, ownership status, etc.
- Multi-select filters work correctly
- Filters update map and list views in real time

## Company Information

### US12 - Company Detail/Profile Page

**As a** user,
**I want to** view company profile pages with detailed information,
**so that** I can understand their offerings, services, and contact information.
**Acceptance Criteria:**
- Profile contains company name, services, contact, and tags
- UI layout is clear and consistent
- Navigation back to map/list view is easy

### US13 - Company News & Trends

**As a** user,
**I want to** view industry news and thought leadership articles related to companies,
**so that** I can stay informed about market trends and insights.
**Acceptance Criteria:**
- News and trends tab is available on company profiles
- Content includes ICN Victoria research team articles
- Articles are relevant to the company's industry or sector

## User Features

### US14 - Export Company Details

**As a** user,
**I want to** export company details to PDF or Excel format,
**so that** I can save, share, or analyze company information offline.
**Acceptance Criteria:**
- Export button is available on company profile pages
- Users can choose between PDF and Excel formats
- Exported files contain all relevant company information (name, contact, services, capabilities, etc.)
- Downloaded files are properly formatted and readable

### US15 - Save/Bookmark Companies

**As a** user,
**I want to** save and bookmark companies into organized folders,
**so that** I can easily access and manage companies of interest for future reference.
**Acceptance Criteria:**
- Users can save/bookmark companies from profile pages or list view
- Free tier users can create one folder for saved companies
- Plus/Premium tier users can create multiple named folders
- Premium tier users can filter and search within their saved companies
- Saved companies persist across sessions

### US16 - Chat/Communications Feature

**As a** plus or premium user,
**I want to** communicate with ICN Victoria through an in-app chat feature,
**so that** I can ask questions and get support without leaving the platform.
**Acceptance Criteria:**
- Chat interface is accessible to Plus and Premium tier users
- Messages are routed to ICN Victoria's research team
- Users receive responses within the application