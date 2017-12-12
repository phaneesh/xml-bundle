# Dropwizard XML Bundle [![Travis build status](https://travis-ci.org/phaneesh/xml-bundle.svg?branch=master)](https://travis-ci.org/phaneesh/xml-bundle)

This bundle adds XML request/response support for dropwizard.
This bundle compiles only on Java 8.
 
## Dependencies
* XML Jackson Data format 2.9.0  

## Usage
The bundle adds XML support based on content negotiation. This makes it easier to switch between legacy friendly and readable protocols. 
 
### Build instructions
  - Clone the source:

        git clone github.com/phaneesh/xml-bundle

  - Build

        mvn install

### Maven Dependency
Use the following repository:
```xml
<repository>
    <id>clojars</id>
    <name>Clojars repository</name>
    <url>https://clojars.org/repo</url>
</repository>
```
Use the following maven dependency:
```xml
<dependency>
    <groupId>io.dropwizard</groupId>
    <artifactId>dropwizard-xml</artifactId>
    <version>1.2.2-1</version>
</dependency>
```

### Using Xml bundle

#### Bootstrap
```java
    @Override
    public void initialize(final Bootstrap...) {
        bootstrap.addBundle(new XmlBundle());
    }
```

#### Resource
```java
    @GET
    @Produces({MediaType.APPLICATION_XML})
    @Path("/example")
    @Metered
    public ExamplePojo example() {
        return ExamplePojo("hello");
    }
```


LICENSE
-------

Copyright 2016 Phaneesh Nagaraja <phaneesh.n@gmail.com>.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.