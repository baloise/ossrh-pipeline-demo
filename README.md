# ossrh-pipeline-demo

## usage

On every push the [continuous release](https://github.com/baloise/ossrh-pipeline-demo/blob/main/.github/workflows/cr.yml) will run.

If the version in the POM is a -SNAPSHOT it will be deployed to the [snapshot repository](https://oss.sonatype.org/content/repositories/snapshots/com/baloise/), otherwise to the [release repository](https://repo1.maven.org/maven2/com/baloise/).

Please note that the maven repos use caching and it may take up to hours until the new artifact is available. You can check the internal status on [https://oss.sonatype.org/](https://oss.sonatype.org/) ( login required).

Please also do not push releases on this demo.

## background

The setup is based on several [secrets available on baloise org level](https://github.com/organizations/baloise/settings/secrets/actions).

* BAOPSO_GPG_46948F68_KEYNAME
* BAOPSO_GPG_46948F68_PASSPHRASE
* BAOPSO_GPG_46948F68_PRIVATE
* OSSRH_PWD_TOKEN
* OSSRH_USER_TOKEN

 They are used in the [cr.yml](https://github.com/baloise/ossrh-pipeline-demo/blob/main/.github/workflows/cr.yml) and the maven [settings.xml](https://github.com/baloise/ossrh-pipeline-demo/blob/main/.github/workflows/cr.yml).
 

## credits and further reading

* code / concept based on [simpligility/ossrh-pipeline-demo](https://bitbucket.org/simpligility/ossrh-pipeline-demo/src/master/)
* https://github.com/crazy-max/ghaction-import-gpg
* https://central.sonatype.org/pages/apache-maven.html

Real world Baloise examples

* https://github.com/baloise/solr-maven-plugin  