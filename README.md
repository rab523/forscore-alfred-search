# forScore Library Search — Preview

Search your forScore scores and bookmarks from Alfred. Press **Return** to open a result or **Command-C** to copy a Markdown link. Results display the icon from your installed forScore app.

> Preview: full-library export reliability is still being tested. Large exports may take a long time or be interrupted.

## Requirements

- A Mac with forScore and its Shortcuts actions.
- Alfred with Powerpack.
- Apple Shortcuts with permission to run the included shell actions.

No separate Python installation is needed to use the tools.

## Install and use

1. Download and open [Export forScore Index - Shared.shortcut](Export%20forScore%20Index%20-%20Shared.shortcut?raw=true).
2. Download and open [forScore Library Search - Shared.alfredworkflow](forScore%20Library%20Search%20-%20Shared.alfredworkflow?raw=true).
3. Open forScore and run **Export forScore Index - Shared** in Shortcuts. Review any permission requests.
4. Keep forScore available and your Mac awake until the shortcut finishes.
5. Open Alfred and type **fsc** followed by a score or bookmark title.

Search also matches the parent PDF filename and ignores case and accents. Up to 200 matches are displayed; narrow the query to find more specific results.

## Refreshing your library

Run the shortcut again after adding, removing, or renaming library items. Links use filenames and bookmark names, so a rename can make an older link stop working.

Only run one export at a time. Each run starts a fresh export and archives earlier progress. The previous completed index stays available until a new export succeeds.

If Alfred says to run the shortcut first, the initial export has not finished successfully. Check Shortcuts for an error or permission request before retrying.

## Local storage and privacy

Each user builds an index from their own forScore library. The downloads contain no scores or library index. The tools do not upload your library.

The index and progress files are stored in:

`~/Library/Application Support/forScore Alfred/`

Here, `~` means the current user's home folder. Exported titles and links are stored locally in that folder.

## Limitations

- Full-library export reliability is still being validated.
- Scores are requested from forScore's current library; multi-library coverage has not been verified.
- Score thumbnails are not included. The forScore icon is read from `/Applications/forScore.app` or `~/Applications/forScore.app`; other install locations use Alfred's default icon.
- This is an independent integration, not an official forScore or Alfred product.

## Source and feedback

Download [the source archive](forScore-Shared-Preview-Source.zip?raw=true) to inspect the workflow and exporter scripts. It includes isolated tests, which developers can run with `python3 -m unittest discover -s tests`.

Report problems through this repository's Issues page. Include the error message and relevant app versions; do not attach your library index or scores.
