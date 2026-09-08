# CLAUDE.md — E SE FÔSSEMOS? / BRASIL EXPERIENCE

## Project mission

Build a premium, cinematic, mobile-first interactive travel experience for a trip from Porto, Portugal to Brazil.

The website is for the creator + Sofia, and potentially additional friends. It is NOT a generic travel agency website and NOT "Sofia's Summer". The creator is trying to convince Sofia, but the product should feel like a shared trip that everyone can join.

Core idea:
> A cinematic simulation of the trip before the trip exists.

Default proposal: 10 days.
Creator's ideal: 12 days.
The user chooses the final duration late in the experience, after desire has been created. Support 7 / 10 / 12 / 14 days.

## Non-negotiable product principles

1. Film first, information second.
2. Mobile is the primary product; desktop is the expanded cinematic version.
3. The opening cinematic should be approximately 45–75 seconds.
4. Do not make the whole website a linear 10-minute movie. After the opening, give the user control.
5. Every major choice should be able to affect route, activities, budget, or narrative where practical.
6. Do not duplicate code for different trips. Use reusable components + trip configuration.
7. Separate content/data from presentation.
8. Never fake live data. Show source + fetched/check timestamp and loading/error/fallback states.
9. Never claim zero snake/fauna risk. Present fauna/safety factually by activity and location.
10. Do not turn the interface into dashboards or travel-agency tables.
11. Use strong typography, negative space, editorial composition, subtle texture, and restrained Brazilian accents.
12. Avoid cliché Carnival/Samba/tourism aesthetics.
13. Do not build the entire experience at once. Build one perfect vertical slice first.

## Visual direction

Concept:
Old-world Brazilian elegance + contemporary everyday life + modern WebGL cinematic technology.

Mood:
luxury without ostentation, nostalgic without sepia, warm, calm, sensual, editorial, coastal, tropical, sophisticated.

Palette:
- Midnight Blue #071E2F
- Ocean Blue #0C4966
- Baby Blue #AFC9D3
- Soft Ocean #6F9EAE
- Warm Beige #E7D7BA
- Sand #D8C09A
- Fog #DCE4E2
- Warm White #FFF8EA
- Sun Yellow #F4B942
- Tropical Green #3D7A58
- Coral #D96C55
- Deep Brazilian Blue #155C78

Rule: roughly 90% muted / 10% expressive accent. Strong Brazilian colours appear as events, not decoration everywhere.

Typography:
Editorial serif for large headlines + clean modern sans for interface/body. Prefer Instrument Serif + Inter (or equivalent if unavailable).

## Opening cinematic

Narrative:
PORTO → airport → departure board → gate → airplane → window → clouds → ocean → Sugarloaf/Rio.

Suggested beats:
1. Black / atmospheric intro.
2. Porto geographic coordinates.
3. Cinematic 3D departure board inspired by Porto Airport. Do not attempt an exact full airport replica.
4. Flight line: Porto → Rio de Janeiro / GIG.
5. Camera leaves board and travels through simplified airport environment.
6. Gate.
7. Airplane.
8. Window.
9. Clouds.
10. Atlantic.
11. Pão de Açúcar appears through atmosphere.
12. Sound/music changes.
13. “RIO DE JANEIRO”.
14. “E SE FÔSSEMOS?”
15. Transition into exploration.

The airport should feel like an environment, not a 3D demo. Use 3D for camera, depth, fog, board, silhouettes, lighting; use video/photo where real imagery is more convincing.

## Interaction model

After opening:
“WHAT KIND OF TRIP?” / equivalent.

Preference dimensions:
- beach
- nature
- photography
- food
- nightlife
- relaxation
- adventure
- roadtrip
- iconic sights

Budget: configurable.
Travellers: default 2, expandable.
Duration: initially hidden/default 10; final duration selection later.

Trip state should be centralized (e.g. Zustand):
travellers, days, budget, preferences, selected destinations, selected activities, accommodation tier, transport choices.

Recommendation engine scores destinations and trip configurations, but UI should translate scores into editorial language, not expose raw dashboards.

## Trip candidates

Master candidate:
- Rio de Janeiro — 4 nights
- Búzios — 3 nights
- Paraty / Trindade — 3 nights
= 10 nights / approximately 11 days depending on flight-day convention.

Important: the project should distinguish “10 days” from “10 nights” explicitly once dates are known. Do not silently equate them.

Alternatives:
1. Golden Summer — Rio 4 + Búzios 4
2. Brazilian Roadtrip — Rio 4 + Búzios 3 + Paraty 3
3. Into The Wild — Rio 4 + Paraty 3 + Ilha Grande 3
4. All In — Rio 4 + Búzios 3 + Paraty 4 + Ilha Grande 2

These are candidate configurations, not final bookings.

## Experiences

Prioritize memorable experiences:
- Pão de Açúcar
- Cristo Redentor
- Arpoador / sunset
- Mirante Dona Marta
- hang gliding / paragliding where safely and legally available
- helicopter golden-hour flight
- boat day
- beaches
- surf / water activities
- road/motorbike-at-sunset aesthetic where legal, insured, and appropriate
- Atlantic Forest / preserved beaches
- Praia do Sono as a possible day/experience, comfort permitting
- slow hotel/rest day
- curated dinners and cocktails

Create experience tiers:
SLOW / ICONIC / ADVENTURE / DREAM.

Experiences must show practical information in an elegant detail overlay:
duration, approximate cost when known, effort, transport, accessibility, wildlife/fauna exposure, safety notes, booking requirements.

Never invent prices, availability, operators, or safety claims.

## Hotel concept

Include one standout “THE RESET” stay in a suitable destination.
Narrative:
“After a few days discovering Brazil, we do nothing.”

Presentation should be editorial:
stone, wood, linen, pool, vegetation, sea, breakfast, hammock, quiet.

Use SMART / BALANCED / DREAM accommodation tiers elsewhere.

Do not present hotels as booking-site tables.

## Travel map

The map must belong to the site's visual language:
- beige
- baby blue
- muted ocean blue
- warm white
- desaturated green
- thin editorial lines
- subtle paper/topographic texture
- occasional saturated Brazilian accent colours

It should feel like a refined digital nautical/editorial chart, not Google Maps.

Route is animated and state-driven.
Examples:
Porto → Rio flight
Rio → Búzios road
Búzios → Paraty road
Paraty → Ilha Grande maritime option

## Counter system

Build reusable animated counters for:
- flight duration
- road transfer duration
- distance
- “time until golden hour”
- nights
- trip duration
- walking time to beach
- etc.

Counters are narrative UI, not dashboard widgets.
Travel durations should come from data/services when possible and be clearly labeled as estimated/planned.

Example:
RIO → BÚZIOS
02h 35m
BY CAR

The animated countdown is illustrative unless it represents an actual live countdown.

## Branching scenes

Choices can change:
- activities
- route
- budget
- duration
- accommodation
- recommendation
- scene/media

Example:
Helicopter YES → golden-hour aerial scene + budget update.
Helicopter NO → ground sunset alternative + lower budget.

The branching should be meaningful but not create an unmaintainable combinatorial explosion. Use controlled variants.

## Shareability

The final product may be shown to friends on mobile.
Support shareable trip configurations/URLs where practical, e.g. /trip/[slug] or a serialized state.
Do not hardcode the experience to Sofia.

## Technical direction

Preferred stack:
- Next.js
- TypeScript
- Tailwind CSS
- GSAP + @gsap/react
- Lenis
- Three.js + @react-three/fiber + @react-three/drei
- Zustand
- Lucide React
- Zod
- optional Mapbox if truly useful
- optional Howler/Web Audio API

Check existing dependencies before installing anything.

Architecture:
app/
  intro/
  discover/
  trips/
  trip/[slug]/
  destinations/[slug]/
  activities/[slug]/
  restaurants/[slug]/
  budget/
  safety/
  itinerary/
  final/

components/
  cinematic/
  map/
  trip/
  editorial/
  ui/

data/
  destinations.ts
  activities.ts
  restaurants.ts
  accommodations.ts
  transport.ts
  trips.ts
  safety.ts
  seasonal.ts

services/
  flights.ts
  weather.ts
  currency.ts
  hotels.ts

lib/
  scoring/
  formatting/
  animation/
  performance/

## Service contracts

FlightProvider:
getFlights(origin, destination, dates) -> FlightResult[]

FlightResult:
airline
origin
destination
departure
arrival
duration
stops
price
currency
fetchedAt
source
dataQuality: live | estimated | manual

Equivalent provenance rules apply to weather, currency, and hotel data.

## Components to consider

CinematicHero
AirportDepartureBoard
AirportEnvironment
FlightTransition
AirplaneWindowScene
SugarloafReveal
Chapter
Scene
ParallaxImage
DepthLayer
RouteMap
TravelCounter
DestinationReveal
ActivityStory
ExperienceCard
StayEditorial
FoodMoment
SafetyDrawer
PriceReveal
TripBuilder
TripCompare
DecisionScene
SoundToggle
ProgressRail
ShareTrip
FinalDecision

Use a common Scene wrapper with destination/theme variants rather than duplicating page logic.

## Performance

Mobile-first:
- respect prefers-reduced-motion
- lazy-load 3D
- use lower DPR on mobile
- pause/offload 3D when not visible
- responsive media
- poster images
- no autoplay audio
- graceful fallback from 3D/video to image
- avoid giant unoptimized assets
- measure Web Vitals
- preserve touch scroll
- never trap scrolling
- avoid heavy 3D on low-power devices

Desktop can enable richer camera motion, cursor parallax, larger WebGL scenes and horizontal moments.

## Audio

Default silent due to browser restrictions.
Visible sound toggle.
Atmospheres:
Porto/airport: subtle terminal ambience
flight: engine/air ambience
Rio: contemporary Brazilian/urban
Búzios: chill/coastal
Paraty: organic/acoustic/nature

Never make sound necessary to understand the site.

## Development strategy

Do NOT implement all pages immediately.

Phase 1:
Perfect 60-second slice:
Porto → departure board → gate → airplane → window → Pão de Açúcar.

Phase 2:
Rio chapter.

Phase 3:
Búzios + route transition.

Phase 4:
Paraty/Trindade + “The Reset”.

Phase 5:
Trip engine + preferences + branching.

Phase 6:
budget, itinerary, safety, restaurants, stays.

Phase 7:
live services.

Phase 8:
mobile/performance/accessibility.

Phase 9:
polish/deployment/shareability.

Use small, reviewable commits.

## GitHub / deployment

Repository should be GitHub-first.
Prefer GitHub + Vercel for production unless static export is sufficient.
Keep environment secrets out of repo.
Use .env.example.
Add README with local setup, architecture and deployment.

## Content/data rules

Never fake live values.
Static editorial content may use placeholders initially but must be clearly marked for replacement.
Research and verify travel times, seasonal suitability, operators, safety, fauna, restaurant/hotel details before final content lock.

## Definition of done

The experience should feel:
- cinematic
- expensive
- calm
- Brazilian without cliché
- personal but not exclusively Sofia-specific
- excellent on iPhone
- richer on desktop
- interactive
- fast enough to actually use
- credible when it shows practical travel data

When a choice exists between adding more features and improving one scene, improve the scene.
