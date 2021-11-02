These notes are for the EDITORS of triffo

This project was created using the [ontology starter kit](https://github.com/cmungall/ontology-starter-kit). See the site for details.

For more details on ontology management, please see the [OBO tutorial](https://github.com/jamesaoverton/obo-tutorial) or the [Gene Ontology Editors Tutorial](go-protege-tutorial.readthedocs.io)

## Editors Version

Make sure you have an ID range in the [idranges file](triffo-idranges.owl)

If you do not have one, get one from the head curator.

The editors version is [triffo-edit.owl](triffo-edit.owl)

** DO NOT EDIT triffo.obo OR triffo.owl in the top level directory **

[../../triffo.owl](../../triffo.owl) is the release version

To edit, open the file in Protege. First make sure you have the repository cloned, see [the GitHub project](https://github.com/cmungall/triffid-behavior) for details.

## ID Ranges

These are stored in the file

 * [triffo-idranges.owl](triffo-idranges.owl)

** ONLY USE IDs WITHIN YOUR RANGE!! **

If you have only just set up this repository, modify the idranges file
and add yourself or other editors. Note Protege does not read the file
- it is up to you to ensure correct Protege configuration.


### Setting ID ranges in Protege

We aim to put this up on the technical docs for OBO on http://obofoundry.org/

For now, consult the [GO Tutorial on configuring Protege](http://go-protege-tutorial.readthedocs.io/en/latest/Entities.html#new-entities)


## Release Manager notes

You should only attempt to make a release AFTER the edit version is
committed and pushed, and the travis build passes.

to release:

    cd src/ontology
    make

If this looks good type:

    make prepare_release

This generates derived files such as triffo.owl and triffo.obo and places
them in the top level (../..). The versionIRI will be added.

Commit and push these files.

    git commit -a

And type a brief description of the release in the editor window

Finally type

    git push origin master

IMMEDIATELY AFTERWARDS (do *not* make further modifications) go here:

 * https://github.com/cmungall/triffid-behavior/releases
 * https://github.com/cmungall/triffid-behavior/releases/new

The value of the "Tag version" field MUST be

    vYYYY-MM-DD

The initial lowercase "v" is REQUIRED. The YYYY-MM-DD *must* match
what is in the versionIRI of the derived triffo.owl (data-version in
triffo.obo).

Release title should be YYYY-MM-DD, optionally followed by a title (e.g. "january release")

Then click "publish release"

__IMPORTANT__: NO MORE THAN ONE RELEASE PER DAY.

The PURLs are already configured to pull from github. This means that
BOTH ontology purls and versioned ontology purls will resolve to the
correct ontologies. Try it!

 * http://purl.obolibrary.org/obo/triffo.owl <-- current ontology PURL
 * http://purl.obolibrary.org/obo/triffo/releases/YYYY-MM-DD.owl <-- change to the release you just made

For questions on this contact Chris Mungall or email obo-admin AT obofoundry.org

# Travis Continuous Integration System

Check the build status here: [![Build Status](https://travis-ci.org/cmungall/triffid-behavior.svg?branch=master)](https://travis-ci.org/cmungall/triffid-behavior)

Note: if you have only just created this project you will need to authorize travis for this repo. Go to [https://travis-ci.org/profile/cmungall](https://travis-ci.org/profile/cmungall) for details

