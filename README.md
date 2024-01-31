= Cloudbees action: Scan with Nexus Lifecycle XC

Use this action to scan repositories for dependency vulnerabilities with Nexus Lifecycle XC, delivered via the Nexus IQ server. Nexus Lifecycle XC is a Sonatype product.

== Inputs

[cols="2a,1a,1a,3a",options="header"]
.Input details
|===

| Input name
| Data type
| Required?
| Description

| `server-url`
| String
| Yes
| The Nexus IQ server name.

| `username`
| String
| Yes
| The Sonatype username.

| `password`
| String
| Yes
| The Sonatype password.

| `token`
| String
| Yes
| The Sonatype token.

| `language`
| String
| No
| The language of your Git repository code base.
Refer to <<_supported_languages>>.

|===

[#_supported_languages]
== Supported languages

[cols="1a,1a",options="header"]
.Supported languages with inputs
|===

| Supported language
| Input format

| Go
| `LANGUAGE_GO`

| Java
| `LANGUAGE_JAVA`

| JavaScript
| `LANGUAGE_JS`

| PHP
| `LANGUAGE_PHP`

| Ruby
| `LANGUAGE_RUBY`

|===

== Usage example

In your YAML file, add:

[source,yaml]
----

      - name: Scan with Nexus IQ server
        uses: cloudbees-io/nexusiq-sca-scan-dependency@v1
        with:
          server-url: ${{ vars.SONATYPE_SERVER_URL }}
          username: "sonatype_username"
          password: ${{ secrets.SONATYPE_PASSWORD }}
          token: ${{ secrets.SONATYPE_TOKEN }}
          language: "LANGUAGE_JAVA"

----

== License

This code is made available under the 
link:https://opensource.org/license/mit/[MIT license].

== References

* Learn more about link:https://docs.cloudbees.com/docs/cloudbees-saas-platform-actions/latest/[using actions in CloudBees workflows].
* Learn about link:https://docs.cloudbees.com/docs/cloudbees-saas-platform/latest/[the CloudBees platform].

       
        
