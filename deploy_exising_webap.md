## Deploying existing webapplication to Azure



```
git clone https://github.com/spring-guides/gs-spring-boot
```


### Configure the azure-webapp maven pluggin 

```bash
mvn com.microsoft.azure:azure-webapp-maven-plugin:1.12.0:config
```

### It will auto configure the plugin with details.
Check and edit as required


```xml
      <plugin>
        <groupId>com.microsoft.azure</groupId>
        <artifactId>azure-webapp-maven-plugin</artifactId>
        <version>1.12.0</version>
        <configuration>
          <schemaVersion>v2</schemaVersion>
          <subscriptionId>a9a6f24a-26c0-483d-8825-c4f0016c13ba</subscriptionId>
          <resourceGroup>CHANGE ME</resourceGroup>
          <appName>CHANGE ME</appName>
          <pricingTier>B1</pricingTier>
          <region>westeurope</region>
          <runtime>
            <os>Linux</os>
            <javaVersion>Java 8</javaVersion>
            <webContainer>Java SE</webContainer>
          </runtime>
          <deployment>
            <resources>
              <resource>
                <directory>${project.basedir}/target</directory>
                <includes>
                  <include>*.jar</include>
                </includes>
              </resource>
            </resources>
          </deployment>
        </configuration>
      </plugin>

```



#### Deploy

```bash
mvn package azure-webapp:deploy
```

