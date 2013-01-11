---

layout: howto
title: Adding gwt-dev.jar to Eclipse classpath with 'm2e' profile
category: gwt
updated_at: 2013-01-11
rendered: site.time

---

Adding gwt-dev.jar to Eclipse classpath with 'm2e' profile
==========================================================

Normally, gwt-maven-plugin adds gwt-dev automatically, but current lifecycle-mapping 
for gwt-maven-plugin prevent this from happening, because Eclipse is not able to handle it. 
Eclipse projects managed by m2e, which depend on gwt-dev, need to add a copy of this profile 
```xml
<profile>
	<id>m2e</id>
	<activation>
		<property>
			<name>m2e.version</name>
		</property>
	</activation>
  <!-- This can be skiped if no pom decends from this. -->
  <!-- If skipped, remember to move the version tag to -->
  <!-- the pom dependency below -->
	<dependencyManagement>
		<dependencies>
			<dependency>
				<groupId>com.google.gwt</groupId>
				<artifactId>gwt-dev</artifactId>
				<version>${gwt.version}</version>
			</dependency>
		</dependencies>
	</dependencyManagement>
  <!-- Add gwt-dev.jar to this project -->
	<dependencies>
		<!-- Google Window Toolkit (GWT) -->
		<dependency>
			<groupId>com.google.gwt</groupId>
			<artifactId>gwt-dev</artifactId>
		</dependency>
	</dependencies>
  
</profile>
```
to resolve missing imports in Eclipse automatically. This profile should only be activated in 
Eclipse, which m2e does every time the incremental builder is run.

