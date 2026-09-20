# Sarvo Transit — Vedha + Transit Relations

Android WebView app for live Vedic sidereal transit timing using Swiss Ephemeris.

## 3 main pages
1. **Daily Transit**
   - Current 9 graha positions, Rashi, Nakshatra, Pada, motion and speed.
   - Exact Pada/Nakshatra boundary timing for the selected day.
   - **Planet-to-Planet Vedha + Rashi + D1 Drishti** table.
   - Special Moon view: shows Moon's 3 active Sarvatobhadra Vedha lines and which current planet is sitting on those target Nakshatras, with its exact Pada.
   - Shows From→To Vedha, To→From Vedha and Mutual Vedha separately.
   - Shows Same Rashi YES/NO and D1 Drishti A→B / B→A YES/NO.

2. **Monthly Transit**
   - Full month's Nakshatra/Pada boundary list.
   - Planet-to-planet relation checkpoints every 6 hours for Vedha, Same Rashi and D1 Drishti.

3. **Find Transit**
   - Search a planet's entry into a selected Nakshatra/Pada.
   - Shows start time, end time and duration.
   - Planet Relation Search: Moon→Venus, Moon→Mars, etc., over a selected date range.

## Sarvatobhadra Vedha logic
- Sun, Moon, Rahu and Ketu: all three Vedha directions are active.
- Mars, Mercury, Jupiter, Venus and Saturn: direction depends on motion state — Front for normal direct motion, Left for high direct speed, Right for retrograde.
- The app uses the published 9×9 Sarvatobhadra Chakra layout and its three-ray geometry.
- Exact current target planet Pada is shown alongside the target Nakshatra. This is a Star-level Vedha hit with the target's exact Pada displayed; it is not falsely labelled as a separate universal Pada-to-Pada rule where traditions differ.

## D1 Drishti
Parashari-style sign aspects used in the relation table:
- Sun, Moon, Mercury, Venus: 7th
- Mars: 4th, 7th, 8th
- Jupiter: 5th, 7th, 9th
- Saturn: 3rd, 7th, 10th
- Rahu/Ketu: 5th, 7th, 9th (school-dependent option)

The app reports both directions separately, so **Mutual D1** means A aspects B and B aspects A.

## Astrology calculation
- Lahiri sidereal zodiac.
- Sun, Moon, Mars, Mercury, Jupiter, Venus, Saturn, Rahu and Ketu.
- Ketu is derived as Rahu + 180° because the API's mean node is used.
- Nakshatra = 13°20'; Pada = 3°20'.
- Boundary times are refined from Swiss Ephemeris positions.

## Build
GitHub Actions workflow builds `app-debug.apk` with JDK 17, Gradle 8.7 and Android Gradle Plugin 8.6.1.

The app uses live network access, so the phone needs internet.
