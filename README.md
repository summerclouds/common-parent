# common-parent

## Prepare

(1) Set gpg passphrase before release

```
export GPG_TTY=$(tty)
mvn install -P release
```

(2) Update versions.properties and commit the changes with 'prepare <version>'.

(3) Update ~/.m2/settings.xml

```xml
<settings>
  <profile>
    <id>release</id>
    <properties>
      <gpg.passphrase>xxx</gpg.passphrase>
    </properties>
    <servers>
      <server>
        <id>ossrh</id>
        <username>xxx</username>
        <password>xxx</password>
      </server>
    </servers>
  </profile>
</settings>
```

## Deploy release

```
con release
```

Validate if no changes are in the projects. All local changes will be deleted !!!

Validate if the versions are set correctly.

## Post actions

(1) Commit projects if not already commited