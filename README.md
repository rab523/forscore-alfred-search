# forScore Library Search — Shared preview

Search your forScore scores and bookmarks from Alfred. Press Return to open a result, or Command-C to copy a Markdown link. Each result uses the icon from your installed forScore app.

## Install

1. Install forScore for Mac and Alfred with Powerpack. forScore must expose its score and bookmark actions in Shortcuts.
2. Download and open [Export forScore Index - Shared.shortcut](Export%20forScore%20Index%20-%20Shared.shortcut?raw=true) to add it to Shortcuts.
3. Download and open [forScore Library Search - Shared.alfredworkflow](forScore%20Library%20Search%20-%20Shared.alfredworkflow?raw=true) to install it in Alfred.
4. Open forScore and run **Export forScore Index - Shared** in Shortcuts. Review any requested permissions. The shortcut uses shell scripts to save its local index.
5. Wait for the shortcut to finish, then open Alfred and type **fsc** followed by a title. The shared keyword differs from the original personal workflow's `fs` so they can coexist.

## How it works

The shortcut asks forScore for scores in the current library and for bookmarks, creates automation URLs, saves progress, then validates and deduplicates the records. The completed index lives in `~/Library/Application Support/forScore Alfred/forscore-index.tsv`. An interrupted export leaves any previous completed index in place. Only run one export at a time. A new run archives previous progress and starts over.

Search matches titles and parent PDF filenames without regard to case or accents, showing up to 200 results. Links are preserved as supplied by forScore. Re-export after changing filenames, bookmark names, or library contents. These links are not immutable identifiers.

The package contains no scores or personal library index. Each recipient exports their own library. Search and export use macOS's built-in Perl and shell tools; Python is only needed to run the optional development tests.

## Preview status and limitations

The original personal workflow's search, opening scores/bookmarks, and Markdown copying have been checked. The portable writer and search pass automated tests for Unicode search, duplicate removal, Markdown escaping, the result limit, and preserving the previous index on invalid input.

A complete refresh of the revised shortcut has **not yet been verified**. The latest personal run stopped after 1,544 records. The previously recovered personal index remains usable. Large exports are slow; keep the Mac awake and forScore available. This preview should not yet be presented as a stable release.

Score thumbnails are not exported. Result icons come from `~/Applications/forScore.app` or `/Applications/forScore.app`. An app installed elsewhere will use Alfred's default icon. This is an independent integration, not an official forScore or Alfred product.

## Source

Download [the source archive](forScore-Shared-Preview-Source.zip?raw=true) to inspect or modify these files. The current shared exporter is running; full-library completion is still pending.

- `workflow/`: Alfred configuration, search, and URL opener.
- `shortcut-scripts/`: readable copies of the shell actions embedded in the shared shortcut.
- `tests/`: isolated tests; run `python3 -m unittest discover -s tests` from this folder.

For public distribution, start with a GitHub preview release and collect feedback. Alfred recommends sharing on its forum before Gallery consideration: https://alfred.app/submit/
