# gradle-dependency-pinning

I am not able to force a spring-boot version of a dependency that is introduced by a plugin (gretty).

I set this:
```
dependencyManagement {
    dependencies {
        dependency "org.springframework.boot:spring-boot-starter-web:1.5.9.RELEASE"
        dependency "org.springframework.boot:spring-boot-starter:1.5.9.RELEASE"
        dependency "org.springframework.boot:spring-boot-starter-websocket:1.5.9.RELEASE"
    }
}
```
.. but `./gradlew dependencies` still output this:
```
+--- org.springframework.boot:spring-boot-starter-websocket:1.5.4.RELEASE
|    +--- org.springframework.boot:spring-boot-starter:1.5.4.RELEASE -> 1.5.9.RELEASE (*)
|    +--- org.springframework.boot:spring-boot-starter-web:1.5.4.RELEASE (*)
```

Issue at https://github.com/spring-gradle-plugins/dependency-management-plugin/issues/200
