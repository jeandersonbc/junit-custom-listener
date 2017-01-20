Yep... another JUnit listener for you!

I created this one to help me to debug JUnit executions.
My listener is able to tell you which thread and JVM were used on each TC execution.
Not much fancy but may help you if you are running tests in parallel :)


### Getting Started

1. Install my listener in you local Maven repository (.m2) with `mvn install`.
2. Declare a new dependency in your `pom.xml` file:

    ```{xml}
    <dependency>
        <groupId>com.github.jeandersonbc</groupId>
        <artifactId>junit-custom-listener</artifactId>
        <version>1.0-SNAPSHOT</version>
        <scope>test</scope>
    </dependency>
    ```

3. Add the JUnit Custom Runner to your Maven Surefire settings (`pom.xml`):

    ```{xml}
    <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-surefire-plugin</artifactId>
        <version>${SUREFIRE.VERSION}</version>
            <configuration>
                ...
                <properties>
                  <property>
                    <name>listener</name>
                    <value>com.github.jeandersonbc.JUnitCustomRunListener</value>
                  </property>
                </properties>
                ...
        </configuration>
    </plugin>
    ```

3. Run the tests again, and you will see after the execution a summary for each test case.
