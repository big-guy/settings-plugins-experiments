Augment `plugins {}` block to know where the plugin comes from:

settings.gradle:
```
plugins {
    id 'included-settings-plugin' from build(":included-settings-plugin")
}
```

Predefine plugins available in an included build (this could work for non-root build settings plugins):

settings.gradle:
```
includeBuild("included-settings-plugin") {
    publications {
        plugins {
            id 'included-settings-plugin'
        }
    }
}
```

another-build/settings.gradle:
```
plugins {
    id 'included-settings-plugin'
}
```