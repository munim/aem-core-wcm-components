# AEM Sites Core Components
[![CircleCI](https://circleci.com/gh/adobe/aem-core-wcm-components.svg?style=svg)](https://circleci.com/gh/adobe/aem-core-wcm-components)
[![Code Coverage](https://codecov.io/gh/adobe/aem-core-wcm-components/branch/master/graph/badge.svg)](https://codecov.io/gh/adobe/aem-core-wcm-components)

A set of standardized components for AEM 6.3+ that can be used to speed up development of websites.

## Documentation

* [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library.html)
* [Using Core Components](https://docs.adobe.com/docs/en/aem/6-3/author/page-authoring/default-components/core-components.html)
* [Tutorial for building a new site using the Core Components](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop.html)
* [Recording of the AEM GEMS Webinar, Dec 2018](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

## Development
If you're curious about how the next generation of components looks like, a tech preview is made available in the
[`development`](https://github.com/adobe/aem-core-wcm-components/tree/development) branch.

## Contributing

Contributions are welcome! Read the [Contributing Guide](CONTRIBUTING.md) for more information.

## Available Components

* Page authoring components:
  * [Breadcrumb](content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb)
  * [Carousel](content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel)
  * [Content Fragment](extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment)\*
  * [Image](content/src/content/jcr_root/apps/core/wcm/components/image/v2/image)
  * [List](content/src/content/jcr_root/apps/core/wcm/components/list/v2/list)
  * [Language Navigation](content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation)
  * [Navigation](content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation)
  * [Page](content/src/content/jcr_root/apps/core/wcm/components/page/v2/page)
  * [Separator](content/src/content/jcr_root/apps/core/wcm/components/separator/v1/separator)
  * [Sharing](content/src/content/jcr_root/apps/core/wcm/components/sharing/v1/sharing)
  * [Tabs](content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs)
  * [Teaser](content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser)
  * [Text](content/src/content/jcr_root/apps/core/wcm/components/text/v2/text)
  * [Title](content/src/content/jcr_root/apps/core/wcm/components/title/v2/title)
  * [Quick Search](content/src/content/jcr_root/apps/core/wcm/components/search/v1/search)

* Form components:
  * [Form button](content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button)
  * [Form container](content/src/content/jcr_root/apps/core/wcm/components/form/container/v2/container)
  * [Form hidden field](content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden)
  * [Form options field](content/src/content/jcr_root/apps/core/wcm/components/form/options/v2/options)
  * [Form text field](content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text)

Visit the [roadmap wiki page](https://github.com/adobe/aem-core-wcm-components/wiki#roadmap) for upcoming changes.

\* The Content Fragment Component is an extension to the Core Components and must be separately downloaded and explicitly enabled.

## Component Versioning

The components' versioning scheme is documented on the [AEM Core WCM Components' versioning policies](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) wiki page.

## System Requirements

The latest version of the Core Components, require the below minimum system requirements:

Core Components | Extension | AEM 6.4 | AEM 6.3 | Java
----------------|-----------|---------|---------|------
[2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 1.0.10 | 6.4.2.0 | 6.3.3.0 | 1.8

For a list of requirements for previous versions, see [Historical System Requirements](VERSIONS.md).

## Installation

To install everything, excluding extensions and examples, the [released aggregate package `core.wcm.components.all`](https://github.com/adobe/aem-core-wcm-components/releases) can be installed via the AEM Package Manager.

For more information about the Package Manager please have a look at [How to Work With Packages](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/package-manager.html) documentation page.

## Build

The project has the following minimal requirements:
* Java SE Development Kit 8 or newer
* Apache Maven 3.3.1 or newer

For ease of build and installation the following profiles are provided:

 * ``autoInstallSinglePackage`` - install everything to an existing AEM author instance, as specified by ``http://${aem.host}:${aem.port}``
 * ``autoInstallSinglePackagePublish`` - install everything to an existing AEM publish instance, as specified by ``http://${aem.publish.host}:${aem.publish.port}``
 * ``autoInstallPackage`` - installs the package/bundle to an existing AEM author instance, as specified by ``http://${aem.host}:${aem.port}``
 * ``autoInstallPackagePublish`` - installs the package/bundle to an existing AEM publish instance, as specified by ``http://${aem.publish.host}:${aem.publish.port}``

### UberJar

This project relies on the unobfuscated AEM 6.3 cq-quickstart. This is publicly available on https://repo.adobe.com

For more details about the UberJar please head over to the
[How to Build AEM Projects using Apache Maven](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/ht-projects-maven.html) documentation page.

### Install everything

You can install everything needed to use the components on your running AEM instance by issuing the following command in the top level folder of the project:

    mvn clean install -PautoInstallSinglePackage

### Individual packages/bundles

You can install individual packages/bundles by issuing the following command in the top level folder of the project:

    mvn clean install -PautoInstallPackage -pl <project_name(s)> -am

Please note that

 * ``-pl/-projects`` option specifies the list of projects that you want to install
 * ``-am/-also-make`` options specifies that dependencies should also be built

## Include core components as subpackage into your own project maven build

The released version of the core components are available on the public maven repository at https://repo.adobe.com. To include the
core components package into your own project maven build you can add the dependency
 ```
 <dependency>
     <groupId>com.adobe.cq</groupId>
     <artifactId>core.wcm.components.all</artifactId>
     <type>zip</type>
     <version>2.2.0</version>
 </dependency>
 ```

 and sub package section
```
 <subPackage>
     <groupId>com.adobe.cq</groupId>
     <artifactId>core.wcm.components.all</artifactId>
     <filter>true</filter>
 </subPackage>
```

 to the `content-package-maven-plugin`.

 For more information how to setup the Adobe Maven Repository (`repo.adobe.com`) for your maven build, please have a look at the
 related [Knowledge Base article](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html)
