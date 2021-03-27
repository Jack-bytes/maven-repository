# Maven Repository For Everyone

### information
- **author :** Jack
- **contact me :** Tencent QQ 78700393


### What is this repository for;

    To store maven jar, the repository url is https://maven.pkg.github.com/jack-bytes/maven-repository;

### How to use this repository;

- add the code following this line into your maven setting.xml;

```xml
<settings>

    <!-- if the setting.xml already have a servers tag, please just append server tag into servers; -->
    <servers>
        <server>
            <id>github</id>
            <username>jack-bytes</username>
            <password>replace with github token, please get from author of this repository</password>
        </server>
    </servers>
    
    <mirrors>
        <mirror>
            <id>ali</id>
            <name>ali Maven</name>
            <mirrorOf>*,!github</mirrorOf>
            <url>https://maven.aliyun.com/repository/public/</url>
        </mirror>
    </mirrors>
    
    <profiles>
        <profile>
            <id>github-repo</id>
            <activation>
                <activeByDefault>true</activeByDefault>
            </activation>
            <repositories>
                <repository>
                    <id>github</id>
                    <name>GitHubRepository</name>
                    <url>https://maven.pkg.github.com/jack-bytes/maven-repository</url>
                    <layout>default</layout>
                    <releases>
                        <enabled>true</enabled>
                        <updatePolicy>daily</updatePolicy>
                    </releases>
                    <snapshots>
                        <enabled>true</enabled>
                        <updatePolicy>always</updatePolicy>
                    </snapshots>
                </repository>
            </repositories>
        </profile>
    </profiles>
</settings>
```
- add dependency to pom.xml in your project ;