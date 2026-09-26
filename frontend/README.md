# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Oxc](https://oxc.rs)
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/)

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.


src/
├── index.css                  # Global resets & CSS variables (colors, spacing, fonts)
├── app/                       # App entry, routing, and provider setup
│   ├── App.tsx                # Root component
│   ├── App.css                # Root-level styles
│   ├── router.tsx             # Route definitions (react-router)
│   └── providers.tsx          # Wraps app in context providers (auth, ride state, etc.)
├── assets/                    # Images, icons, fonts
├── components/
│   └── ui/                    # Shared UI building blocks used across passenger & driver
│       ├── Button.tsx         # Primary/outline button variants
│       ├── Button.css
│       ├── InputField.tsx     # Labeled input field
│       ├── InputField.css
│       ├── Card.tsx           # Generic card container
│       ├── Card.css
│       ├── Toggle.tsx         # On/off switch (e.g. driver availability)
│       ├── Toggle.css
│       ├── Avatar.tsx         # User/driver profile image
│       └── Avatar.css
├── layouts/                   # Shared page shells (nav bars, structure)
│   ├── PassengerLayout.tsx    # Top/Bottom nav wrapper for passenger screens
│   ├── PassengerLayout.css
│   ├── DriverLayout.tsx       # Top nav wrapper for driver screens
│   └── DriverLayout.css
├── features/                  # App logic grouped by role/domain
│   ├── auth/                  # Login & sign-up flow (shared by both roles)
│   │   ├── pages/
│   │   │   ├── LoginSignUp.tsx
│   │   │   └── LoginSignUp.css
│   │   ├── components/        # Auth-specific components
│   │   └── api/                # Auth-related API calls
│   ├── passenger/              # Passenger-facing screens & logic
│   │   ├── pages/
│   │   │   ├── Home.tsx              # Book a Ride
│   │   │   ├── Home.css
│   │   │   ├── FindingDriver.tsx     # Live tracking while driver is en route
│   │   │   ├── FindingDriver.css
│   │   │   ├── TripComplete.tsx      # Rate & pay after trip ends
│   │   │   ├── TripComplete.css
│   │   │   ├── AddressSearch.tsx     # Pickup/drop-off location search
│   │   │   ├── AddressSearch.css
│   │   │   ├── PaymentMethod.tsx     # Select cash/GCash/card
│   │   │   ├── PaymentMethod.css
│   │   │   ├── NoDriversFound.tsx    # Empty state when no drivers nearby
│   │   │   ├── NoDriversFound.css
│   │   │   ├── CancelRideConfirm.tsx # Confirm ride cancellation
│   │   │   ├── CancelRideConfirm.css
│   │   │   ├── MyRides.tsx           # Ride history list
│   │   │   ├── MyRides.css
│   │   │   ├── Profile.tsx           # Passenger profile & settings
│   │   │   ├── Profile.css
│   │   │   ├── Safety.tsx            # SOS / emergency screen
│   │   │   └── Safety.css
│   │   ├── components/          # Passenger-only components (e.g. DriverCard, MapView)
│   │   └── api/                  # Passenger-related API calls
│   └── driver/                   # Driver-facing screens & logic
│       ├── pages/
│       │   ├── Home.tsx                 # Availability toggle & daily summary
│       │   ├── Home.css
│       │   ├── IncomingRideRequest.tsx  # New ride request w/ accept/decline
│       │   ├── IncomingRideRequest.css
│       │   ├── TripInProgress.tsx       # Active trip navigation screen
│       │   ├── TripInProgress.css
│       │   ├── ArrivedAtPickup.tsx      # Waiting for passenger at pickup
│       │   ├── ArrivedAtPickup.css
│       │   ├── RideRequestExpired.tsx   # Request timeout state
│       │   ├── RideRequestExpired.css
│       │   ├── CancelRideConfirm.tsx    # Confirm trip cancellation
│       │   ├── CancelRideConfirm.css
│       │   ├── SignUpDocuments.tsx      # License/vehicle doc upload
│       │   ├── SignUpDocuments.css
│       │   ├── VerificationPending.tsx  # Awaiting document approval
│       │   ├── VerificationPending.css
│       │   ├── EarningsPayout.tsx       # Earnings summary & cash out
│       │   ├── EarningsPayout.css
│       │   ├── RideHistory.tsx          # Completed trips list
│       │   ├── RideHistory.css
│       │   ├── Profile.tsx              # Driver profile & vehicle details
│       │   ├── Profile.css
│       │   ├── Safety.tsx               # SOS / emergency screen
│       │   └── Safety.css
│       ├── components/           # Driver-only components
│       └── api/                   # Driver-related API calls
├── hooks/                         # Shared custom hooks (useGeolocation, useAuth)
├── lib/                           # API client, socket setup, maps SDK wrapper
├── store/                         # Global state (ride status, auth session)
├── types/                         # Shared TypeScript types/interfaces
├── utils/                         # Helper functions
└── constants/                     # App-wide constants (routes, config values)