# mastodon-lists

Currently, Mastodon does not support making lists public, so I am using this
repository to share mine with everyone.

Each CSV file in this repository is its own list, which was exported using
[mastodon-listmanager][mastodon-listmanager].

| Name                | Description                                          |
|---------------------|------------------------------------------------------|
| Actors and Creators | Actors, artists, musicians, and other creative types |
| Geopolitics         | International policy experts and institutions        |
| Healthcare          | Health experts and agencies                          |
| InfoSec             | Anyone or anything related to information security   |
| Journalism          | Journalists and media outlets                        |
| NatSec              | US national security experts and agencies            |
| STEM                | Scientists, technologists, developers, and such      |
| US Politics         | US politicians, pundits, and interest groups         |

Accounts may be in multiple lists. For example, many of the accounts in the
NatAec list are also in the Geopolitics list.

## Importing lists

The CSVs are designed to work with the import followers feature in the native
Mastodon web interface, or [mastodon-listmanager][mastodon-listmanager].

### Mastodon web interface

The native Mastodon web interface includes the ability to import a list of followers from a CSV file. However, it only follows the accounts and
**does not add them to a list**.

Use the following steps:

1. Login to your account
2. Click Preferences
3. Click Import and Export
4. Click Import
5. Select the Following List Import Type
6. Click browse and select the CSV file
7. Select Merge
8. Click Upload

### mastodon-listmanager

[mastodon-listmanager][mastodon-listmanager] is a CLI tool and Python module
that can import and export lists. For example to import the `US Politics.csv`
file into a list called `US Politics`, use the following command.

> ./listmanager.py import list "US Politics.csv" "US Politics"

If the destination list does not exist it will be created automatically. In
Mastodon, only accounts you are following can be added to a list, so the script will
attempt to follow each account before adding it to a list. An account cannot be
added to a list if a follow request is pending.

[mastodon-listmanager]: https://github.com/seanthegeek/mastodon-listmanager
