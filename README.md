# NAD for Home Assistant

This repository is a maintained fork of the NAD custom integration for Home Assistant.

It exists to keep a stable version for deployments that use NAD receivers over Telnet or TCP, with a focus on startup reliability and reconnect behavior.

## What this fork changes

- retries one command after a Telnet/TCP transport failure by recreating the connection
- keeps coordinator listener state per instance
- avoids media player startup crashes when `Main.Source` is temporarily unavailable
- adds safer handling for empty command responses during power, mute, and source operations

## Installation

### HACS

[![Open your Home Assistant instance and add this repository inside HACS.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=Wise-Technology-Poland&repository=homeassistant-nad&category=integration)

1. Open `HACS -> Integrations`.
2. Open `Custom repositories`.
3. Add this repository as category `Integration`.
4. Install `NAD`.
5. Restart Home Assistant.

### Manual

Copy `custom_components/nad` into your Home Assistant `config/custom_components/` directory and restart Home Assistant.

## Setup

After restart:

1. Open `Settings -> Devices & Services`.
2. Add the `NAD` integration.
3. Configure the receiver using Serial, Telnet, or TCP, depending on your installation.

## Notes

- This fork was prepared for a Home Assistant setup using a NAD T785 over Telnet.
- Home Assistant storage settings such as `pref_disable_polling` are not part of this repository.

## Upstream

Original repository: https://github.com/rrooggiieerr/homeassistant-nad
