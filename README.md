# nuxeo-field-validator-plugin

## Synopsis

This Nuxeo plugin implements some common field validators for forms. It must be used from another plugin (the one you are developing).

## Code Example

Use it in your contribution (extensions.xml):
```xml
	<widget name="EmailAddress" type="text">
		<labels>
			<label mode="any">label.email</label>
		</labels>
		<translated>true</translated>
		<fields>
			<field>MyApp:EmailAddress</field>
		</fields>
		<properties mode="edit">
			<property name="validator">#{bFieldValidator.validateEmailAddress}</property>
		</properties>
	</widget>
```

## Motivation

There are a lot of common validations across any web application that could be centralized in one plugin to contribute to Nuxeo platform.

## Installation

You just have to compile the pom.xml using Maven and deploy the plugin in 
```{r, engine='bash', count_lines}
cd nuxeo-field-validator-plugin
mvn clean install
cp target/fieldValidator-*.jar $NUXEO_HOME/nxserver/plugins
```
And then, restart your nuxeo server and enjoy.
