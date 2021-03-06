## init

Initialize an empty package

<link rel="stylesheet" type="text/css" href="/kpt/gifs/asciinema-player.css" />
<asciinema-player src="/kpt/gifs/pkg-init.cast" speed="1" theme="solarized-dark" cols="100" rows="26" font-size="medium" idle-time-limit="1"></asciinema-player>
<script src="/kpt/gifs/asciinema-player.js"></script>

    # run the tutorial from the cli
    kpt tutorial pkg init

[tutorial-script]

### Synopsis

**init is optional**; any directory containing Kubernetes Resource Configuration may be treated as
remote package without the existence of additional packaging metadata.

* Resource Configuration may be placed anywhere under DIR as *.yaml files.
* DIR may contain additional non-Resource Configuration files.
* DIR must be pushed to a git repo or repo subdirectory.

Init will augment an existing local directory with packaging metadata to help
with discovery.

Init will:

* Create a Kptfile with package name and metadata if it doesn't exist
* Create a README.md for package documentation if it doesn't exist.


    kpt pkg init DIR [flags]

  DIR:

    Init fails if DIR does not exist

  --description string

    short description of the package. (default "sample description")

  --name string

    package name.  defaults to the directory base name.

  --tag strings

    list of tags for the package.

  --url string

    link to page with information about the package.

### Examples

    # writes Kptfile package meta if not found
    mkdir my-pkg
    kpt pkg init my-pkg --tag kpt.dev/app=cockroachdb --description "my cockroachdb implementation"

###

[tutorial-script]: ../gifs/pkg-init.sh
