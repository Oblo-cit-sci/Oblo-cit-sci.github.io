# Settings

*Base class for settings, allowing values to be overridden by environment variables. This is useful in production for secrets you do not wish to save in code, it plays nicely with docker(-compose),
Heroku and any 12 factor app design.*

## Properties

- **`ENV`** *(string)*: Must be one of: `['dev', 'prod', 'test']`.
- **`HOST`** *(string)*: Host address(including port) of the frontend app. Default: `http://0.0.0.0`.
- **`PORT`** *(integer)*: Port of the server. Default: `8100`.
- **`POSTGRES_HOST`** *(string)*: hostname of the postgres (e.g. localhost).
- **`POSTGRES_USER`** *(string)*: username for postgres.
- **`POSTGRES_PASSWORD`** *(string)*: password to the postgres database.
- **`POSTGRES_DB`** *(string)*: name of the database.
- **`FIRST_ADMIN_EMAIL`** *(string)*: email address of the 1. admin user.
- **`FIRST_ADMIN_PASSWORD`** *(string)*: Password for the 1. admin user.
- **`EMAIL_ENABLED`** *(boolean)*: Set if emails should be sent. Default: `False`.
- **`EMAIL_SENDER`** *(string)*: (REQUIRED, when EMAIL_ENABLED):  Name of the sender, including the server.
- **`EMAIL_ACCOUNT`** *(string)*: (REQUIRED, when EMAIL_ENABLED): Email address of the sender.
- **`EMAIL_PWD`** *(string)*: (REQUIRED, when EMAIL_ENABLED): Password of the email  account. Default: ``.
- **`EMAIL_SSL_SERVER`** *(string)*: (REQUIRED, when EMAIL_ENABLED): smtp-server of email account. Default: ``.
- **`SESSION_SECRET`** *(string)*: A generic secret to be used for session encryption.
- **`MAP_DEFAULT_MAP_STYLE`** *(string)*: Default mapbox map style to render maps. This is the default style to use. More info: mapbox.com/.
- **`MAP_ACCESS_TOKEN`** *(string)*: Mapbox access token.
- **`ADDITIONAL_MAP_STYLES`** *(array)*: Additional map styles (experimental). Default: `[]`.
  - **Items** *(string)*
- **`PLATFORM_TITLE`** *(string)*: The title of the platform. Visible on the appbar, when no-domain. Default: `Oblo`.
- **`BASE_ROUTER_PREFIX`** *(string)*:  Api endpoint base router prefix. Default: `/api`.
- **`APP_DIR`** *(string)*: The directory where the frontend-app is located, relatively to the app path (default: fe). Default: `fe`.
- **`APP_ROUTE`** *(string)*: application path the frontend app is hooked to. Default: `/`.
- **`BASE_DATA_FOLDER`** *(string)*: Base data folder, where application files (not static files) are stored. Default: `data`.
- **`INIT_DOMAINS_SUBPATH`** *(string)*: Sub-path to the folder where the initial domains are stored, within BASE_DATA_FOLDER/init_files/. Default: `domains`.
- **`LANGUAGE_SQLITE_FILE_PATH`** *(string)*: path of the messages.sqlite database. Default: `messages.sqlite`.
- **`DEFAULT_LANGUAGE`** *(string)*: configured application default language. Default: `en`.
- **`INIT_DOMAINS`** *(boolean)*: Configuration, if domains should be re-initialized during startup. Default: `True`.
- **`INIT_TEMPLATES_CODES`** *(boolean)*: Configuration, if templates and code entries should be re-initialized during startup. Default: `True`.
- **`INIT_LANGUAGE_TABLES`** *(boolean)*: Configuration, if language tables should be re-initialized during startup. Default: `True`.
- **`REPLACE_MESSAGES`** *(boolean)*: Configuration, if messages during re-initialization should be overwritten by text in csv files. Default: `False`.
- **`DEACTIVATE_LANGUAGES`** *(array)*: languages that should be deactivated. Default: `[]`.
  - **Items** *(string)*
- **`LOGIN_REQUIRED`** *(boolean)*: Configuration, if login is required for all routes (experimental). Default: `False`.
- **`EMAIL_VERIFICATION_REQUIRED`** *(boolean)*: Configuration, if email verification is required after registration. Default: `True`.
- **`DEFAULT_USER_GUIDE_URL`** *(string)*: URL to the user guides.
- **`TIMING_MIDDLEWARE_ACTIVE`** *(boolean)*: Configuration, if timing middleware should be active. Default: `False`.
- **`DATA_MIGRATION`** *(boolean)*: Configuration, if data migration should be performed after setup. Default: `False`.
- **`RUN_APP_TESTS`** *(boolean)*: Configuration, if app tests should be run after setup. Default: `False`.
- **`LANGUAGE_LIST_SOURCE_REPO_URL`** *(string)*: Repo from which language names are taken (downloaded at the first startup). Default: `https://github.com/umpirsky/language-list`.
- **`CORS_OTHER_ORIGINS`** *(string)*: Default: ``.
- **`MIGRATION_HELP_ACTIVE`** *(boolean)*: change some config helping and adaptations to the init code for migration. Default: `False`.
- **`ADD_CSP_HEADER`** *(boolean)*: Default: `False`.
- **`CSP_HEADER`** *(string)*: Default: `default-src 'self';`.
- **`MODEL_CONFIG_EXTRA`** *(string)*: Must be one of: `['allow', 'forbid', 'ignore']`. Default: `forbid`.
- **`RESET_TEST_DB`** *(boolean)*: Completely clear the db at startup. Only works in test env. Default: `False`.
- **`DEFAULT_LANGUAGE_FE_MESSAGES_FILE`** *(string)*: A i18n source file that is generally stored in the frontend development repo (works only in dev mode).
