---
name: "\U0001F30D Environment request"
about: "Request a WordPress environment for this project."
title: "[Staging/Acceptance/Production/Legacy] Environment"
labels: enhancement
assignees: sebask

---

## Requirements
The following requirements are needed:
| Requirement | Description |
| :--- | :--- |
| Domain | `example.com`, `www.example.com` |
| WordPress version | `latest` |
| WordPress language | `Dutch` |
| WordPress email address | `info@example.com` |
| WordPress mail service | `WP SMTP Mail`, `Server` |
| WordPress mail provider | `Office 365`, `TransIP` |
| CI/CD workflow | `GitHub Actions` |
| Basic Auth protection | `No` |

## Configuration
The following values should be (un)set for PHP (`php.ini`):
| Variable | Value |
| :--- | :--- |
| `post_max_size` | `50M` |
| `upload_max_filesize` | `50M` |

The following defaults should be (un)set for WordPress (`wp-config.php`):
| Variable | Value |
| :--- | :--- |
| `WP_ENVIRONMENT_TYPE` | `staging`, `production` |
| `WP_ALLOW_MULTISITE` | `false` |
| `FORCE_SSL_ADMIN` | `false`, `true` |
| `DISALLOW_FILE_EDIT` | `true` |
| `WP_DEBUG` | `true`, `false` |

<details>
<summary>Configuration snippet</summary>

```php
/**
 * Set Environment
 *
 * @link https://wordpress.org/support/article/editing-wp-config-php/#wp-environment-type
 */
define('WP_ENVIRONMENT_TYPE', 'production');

/**
 * Enable Multisite/Network
 *
 * @link https://wordpress.org/support/article/editing-wp-config-php/#enable-multisite-network-ability
 */
define('WP_ALLOW_MULTISITE', false);

/**
 * Force SSL for admin screens
 *
 * @link https://developer.wordpress.org/reference/functions/force_ssl_admin/
 */
define('FORCE_SSL_ADMIN', true);

/**
 * Disable the Plugin and Theme File Editor
 *
 * @link https://wordpress.org/support/article/editing-wp-config-php/#disable-the-plugin-and-theme-file-editor
 */
define('DISALLOW_FILE_EDIT', true);

/**
 * For developers: WordPress debugging mode.
 *
 * Change this to true to enable the display of notices during development.
 * It is strongly recommended that plugin and theme developers use WP_DEBUG
 * in their development environments.
 *
 * For information on other constants that can be used for debugging,
 * visit the documentation.
 *
 * @link https://wordpress.org/support/article/debugging-in-wordpress/
 */
define( 'WP_DEBUG', false );

if ( WP_DEBUG ) {
  define( 'WP_DEBUG_LOG', true );
  define( 'WP_DEBUG_DISPLAY', true );
  define( 'CONCATENATE_SCRIPTS', false );
  define( 'SAVEQUERIES', true );
  define( 'SCRIPT_DEBUG', true );
}
```
</details>

## Plugins
The following plugins should be (un)installed:

| Plugin | Status | License |
| :--- | :--- | :--- |
| Akismet Anti-Spam | `uninstalled` | `-` |
| Editor Block Outline | `?` | `-` |
| Gravity Forms | `?` | [Yes](https://www.gravityforms.com/my-account/licenses/) |
| Hello Dolly | `uninstalled` | `-` |
| Plausible Analytics | `?` | [Yes](https://`Plausible`.io/login) |
| Redirection | `?` | `-` |
| Two Factor | `?` | `-` |
| WP All Import Pro | `?` | [Yes](https://www.wpallimport.com/portal/) |
| WP Mail SMTP | `?` | `-` |
| Yoast SEO | `?` | `-` |

<details>
<summary>WP-CLI commands</summary>

```sh
wp plugin uninstall akismet
wp plugin uninstall hello
```
</details>

## Settings
The following settings should be (un)set.

| Setting | Value | Location |
| :--- | :--- | :--- |
| Site Title | `Example` | `WordPress/General` |
| Tagline | `This is an example` | `WordPress/General` |
| WordPress Address | `https://example.com` | `WordPress/General` |
| Site Address | `https://example.com` | `WordPress/General` |
| Administration Email Address | `wordpress@brthrs.nl` | `WordPress/General` |
| Membership | `0` | `WordPress/General` |
| New User Default | `Subscriber` | `WordPress/General` |
| Site Language | `Nederlands` | `WordPress/General` |
| Timezone | `Amsterdam` | `WordPress/General` |
| Date Format | `j F Y` | `WordPress/General` |
| Time Format | `H:i` | `WordPress/General` |
| Week Starts On | `Monday` | `WordPress/General` |
| Homepage | `-` | `WordPress/Reading` |
| Posts page | `-` | `WordPress/Reading` |
| Search engine visibility | `0` | `WordPress/Reading` |
| Pingback flag | `0` | `WordPress/Discussion` |
| Ping status | `0` | `WordPress/Discussion` |
| Comments status | `0` | `WordPress/Discussion` |
| Comment registration | `1` | `WordPress/Discussion` |
| Comment moderation | `1` | `WordPress/Discussion` |
| Thumbnail size | `240 x 240` | `WordPress/Media` |
| Medium size | `512 x 512` | `WordPress/Media` |
| Large size | `1024 x 1024` | `WordPress/Media` |
| Common Settings | `Post name` | `WordPress/Permalinks` |
| Domain Name | `example.com` | `Plausible` |
| View your stats in your WordPress dashboard | `Enabled` | `Plausible` |
| Output Default CSS | `On` | `Gravity Forms` |
| Default Currency | `Euro` | `Gravity Forms` |
| Logging | `Off` | `Gravity Forms` |
| Toolbar menu | `Off` | `Gravity Forms` |
| Automatic Background Updates | `On` | `Gravity Forms` |
| No Conflict Mode | `On` | `Gravity Forms` |
| Output HTML5 | `On` | `Gravity Forms` |
| Enable access to the API | `Disabled` | `Gravity Forms/REST API` |
| SEO analysis | `Off` | `Yoast/General/Features` |
| Readability analysis | `Off` | `Yoast/General/Features` |
| Cornerstone content | `Off` | `Yoast/General/Features` |
| Text link counter | `Off` | `Yoast/General/Features` |
| Insights | `Off` | `Yoast/General/Features` |
| Link suggestions | `Off` | `Yoast/General/Features` |
| XML sitemaps | `On` | `Yoast/General/Features` |
| Admin bar menu | `Off` | `Yoast/General/Features` |
| Security | `On` | `Yoast/General/Features` |
| Usage tracking | `Off` | `Yoast/General/Features` |
| REST API: Head endpoint | `Off` | `Yoast/General/Features` |
| Enhanced Slack sharing | `Off` | `Yoast/General/Features` |
| * | `Off` | `Yoast/General/Integrations` |

<details>
<summary>WP-CLI commands</summary>

```sh
wp option set blogname "Example"
wp option set blogdescription "This is an example"
wp option set timezone_string "Europe/Amsterdam"
wp option set blog_public 0
wp option set default_pingback_flag 0
wp option set default_ping_status 0
wp option set default_comment_status 0
wp option set comment_registration 1
wp option set comment_moderation 1
wp option set thumbnail_size_w 256
wp option set thumbnail_size_h 256
wp option set medium_size_w 512
wp option set medium_size_h 512
wp option set large_size_w 1024
wp option set large_size_h 1024
wp option set permalink_structure "/%postname%/"
```
</details>

## Themes
The following themes should be installed: `example`.

<details>
<summary>WP-CLI commands</summary>

```sh
wp theme uninstall twentytwenty
wp theme uninstall twentytwentyone
wp theme uninstall twentytwentytwo
```
</details>

## Users
The following users should be created:

| Username | Email | First name | Last name | Role |
| :--- | :--- | :--- | :--- | :--- |
| `brthrs` | `wordpress@brthrs.nl` | `-` | - |`Brthrs` | `Super Administrator` |
