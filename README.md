# ESP — Smart-Home Display Companion App

A mobile **Progressive Web App** that controls my ESP32-S3 AMOLED wall display over the internet: send messages and photos, set alarms and see the live state of the device.

## Features

- Send text + photo messages that appear on the device screen.
- Set alarms for future days; the device shows the next one on its standby screen.
- Live device status in the top bar: Wi-Fi, battery %, charging.
- Sign-in with Supabase Auth; data and photos stored in Supabase (Postgres + Storage).
- Installable on iPhone home screen, dark AMOLED-friendly UI.

## Architecture

```
Phone (PWA on GitHub Pages)  ──►  Supabase (Auth, Postgres, Storage)  ◄──  ESP32-S3 device (Arduino/C++)
```

The device firmware lives in a separate private repository. It is compiled by **GitHub Actions** and updated **over the air**, so the device can be updated remotely.

## Tech stack

HTML · CSS · JavaScript · PWA (manifest, home-screen install) · Supabase REST API · GitHub Pages · ESP32 (Arduino / C++)

## Note on keys

The app only contains Supabase's public *publishable* key, which is designed to be used in the browser. Using the app requires signing in.
