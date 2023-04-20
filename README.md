# Chore Cards for Home Assistant

[![GitHub Release][releases-shield]][releases]
[![GitHub Activity][commits-shield]][commits]
[![License][license-shield]](LICENSE)

[![hacs][hacsbadge]][hacs]
![Project Maintenance][maintenance-shield]
[![BuyMeCoffee][buymecoffeebadge]][buymecoffee]

[![Discord][discord-shield]][discord]
[![Community Forum][forum-shield]][forum]

Cards designed to be used with the [Chore Helper](https://github.com/bmcclure/ha-chore-helper) integration.

- Display single chores
- List, filter, and sort multiple chores
- Mark chores as complete or reschedule them easily
- Coming soon: Create and manage chores from the front-end

## Options

| Name              | Type    | Requirement  | Description                                 | Default             |
| ----------------- | ------- | ------------ | ------------------------------------------- | ------------------- |
| type              | string  | **Required** | `custom:boilerplate-card`                   |
| name              | string  | **Optional** | Card name                                   | `Boilerplate`       |
| show_error        | boolean | **Optional** | Show what an error looks like for the card  | `false`             |
| show_warning      | boolean | **Optional** | Show what a warning looks like for the card | `false`             |
| entity            | string  | **Optional** | Home Assistant entity ID.                   | `none`              |
| tap_action        | object  | **Optional** | Action to take on tap                       | `action: more-info` |
| hold_action       | object  | **Optional** | Action to take on hold                      | `none`              |
| double_tap_action | object  | **Optional** | Action to take on double tap                | `none`              |

## Action Options

| Name            | Type   | Requirement  | Description                                                                                                                            | Default     |
| --------------- | ------ | ------------ | -------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| action          | string | **Required** | Action to perform (more-info, toggle, call-service, navigate url, none)                                                                | `more-info` |
| navigation_path | string | **Optional** | Path to navigate to (e.g. /lovelace/0/) when action defined as navigate                                                                | `none`      |
| url             | string | **Optional** | URL to open on click when action is url. The URL will open in a new tab                                                                | `none`      |
| service         | string | **Optional** | Service to call (e.g. media_player.media_play_pause) when action defined as call-service                                               | `none`      |
| service_data    | object | **Optional** | Service data to include (e.g. entity_id: media_player.bedroom) when action defined as call-service                                     | `none`      |
| haptic          | string | **Optional** | Haptic feedback _success, warning, failure, light, medium, heavy, selection_ | `none`      |
| repeat          | number | **Optional** | How often to repeat the `hold_action` in milliseconds.                                                                                 | `none`       |

## Starting a new card from boilerplate-card

### Step 1

Click the "Use this template" button on the main page and clone the new repository to your machine

### Step 2

Install necessary modules (verified to work in node 8.x)
`yarn install` or `npm install`

### Step 3

Do a test lint & build on the project. You can see available scripts in the package.json
`npm run build`

### Step 4

Search the repository for all instances of "TODO" and handle the changes/suggestions

### Step 5

Customize to suit your needs and contribute it back to the community

## Starting a new card from boilerplate-card with [devcontainer][devcontainer]

Note: this is available only in vscode ensure you have the [Remote Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension installed.

1. Fork and clone the repository.
2. Open a [devcontainer][devcontainer] terminal and run `npm start` when it's ready.
3. The compiled `.js` file will be accessible on
   `http://127.0.0.1:5000/boilerplate-card.js`.
4. On a running Home Assistant installation add this to your Lovelace
   `resources:`

```yaml
- url: 'http://127.0.0.1:5000/boilerplate-card.js'
  type: module
```

_Change "127.0.0.1" to the IP of your development machine._

### Bonus

If you need a fresh test instance you can install a fresh Home Assistant instance inside the devcontainer as well.

1. Run the command `container start`.
2. Home Assistant will install and will eventually be running on port `9123`

## [Troubleshooting](https://github.com/thomasloven/hass-config/wiki/Lovelace-Plugins)

NB This will not work with node 9.x if you see the following errors try installing node 8.10.0

```yarn install
yarn install v1.3.2
[1/4] 🔍  Resolving packages...
warning rollup-plugin-commonjs@10.1.0: This package has been deprecated and is no longer maintained. Please use @rollup/plugin-commonjs.
[2/4] 🚚  Fetching packages...
error @typescript-eslint/eslint-plugin@2.6.0: The engine "node" is incompatible with this module. Expected version "^8.10.0 || ^10.13.0 || >=11.10.1".
error Found incompatible module
info Visit https://yarnpkg.com/en/docs/cli/install for documentation about this command.
```

***

[buymecoffee]: https://www.buymeacoffee.com/benmcclure
[buymecoffeebadge]: https://img.shields.io/badge/buy%20me%20a%20coffee-donate-yellow.svg?style=for-the-badge
[commits-shield]: https://img.shields.io/github/commit-activity/y/bmcclure/ha-chore-cards.svg?style=for-the-badge
[commits]: https://github.com/bmcclure/ha-chore-cards/commits/master
[hacs]: https://github.com/custom-components/hacs
[hacsbadge]: https://img.shields.io/badge/HACS-Custom-orange.svg?style=for-the-badge
[discord]: https://discord.gg/Qa5fW2R
[discord-shield]: https://img.shields.io/discord/330944238910963714.svg?style=for-the-badge
[forum-shield]: https://img.shields.io/badge/community-forum-brightgreen.svg?style=for-the-badge
[forum]: https://community.home-assistant.io/
[license-shield]: https://img.shields.io/github/license/custom-components/blueprint.svg?style=for-the-badge
[maintenance-shield]: https://img.shields.io/badge/maintainer-Ben%20McClure%20%40bmcclure-blue.svg?style=for-the-badge
[releases-shield]: https://img.shields.io/github/release/bmcclure/ha-chore-cards.svg?style=for-the-badge
[releases]: https://github.com/bmcclure/ha-chore-cards/releases
