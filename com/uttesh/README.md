<h3>An PDF reporting plugin for TestNG </h3>



<h4>How to use PDFReport Plugin</h4>
====================================

Download latest version of pdfreport <a href="https://github.com/uttesh/mavenrepos/raw/master/pdfreport/pdfreport/1.0.0/pdfreport-1.0.0.jar">download</a>

To use the reporting plug-in, set the "listeners" attribute of the "testng"
element in your Ant build file.The class names for the pdfreport is:

```
  pdfreport.PDFReportListener
```

You may also want to disable the default TestNG reporters by setting the
"useDefaultListeners" attribute to "false".

Your Ant task will probably look something like this:

```
  <testng classpathref="test-path"
          outputdir="${test-results.dir}"
          haltonfailure="true"
          useDefaultListeners="false"
          listeners="pdfreport.PDFReportListener">
    <sysproperty key="pdfreport.title" value="My Test Report"/>
  </testng>
 ``` 

For Maven pom.xml configuration is add the dependecy.
  
          <dependency>
            <groupId>pdfreport</groupId>
            <artifactId>pdfreport</artifactId>
            <version>1.0.0</version>
          </dependency>
          
and add reporsitory in <repositories>

        <repository>
            <id>git-uttesh</id>
            <name>uttesh's Git based repo</name>
            <url>https://github.com/uttesh/mavenrepos/raw/master</url>
        </repository>

we can configure the listner in the testng suite xml file of application also.

```
<?xml version="1.0" encoding="UTF-8"?>
<suite name="Simple Reporter Suite">
  <listeners>
    <listener class-name="pdfreport.PDFReportListener" />
  </listeners>

  <test name="Simple Reporter test">
    <classes>
      <class name="xyz" />
      <class name="abc" />
    </classes>
  </test>
</suite>
```

contributions
=============

First of all price goes to <a href="http://www.jfree.org/jfreechart/">jfree</a> and <a href="http://itextpdf.com/">itext</a> open source jar file which i used to generate the pdf report and pie chart statistic graph.

Developer : [@uttesh](https://twitter.com/uttesh) ( my self ;) )


