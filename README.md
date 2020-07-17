# Groovy-Translator-Tool
Kotlin DSL to Groovy translator tool *help with Debian Gradle version*.

General things to be taken care of:

<table>
    <th>Description</th>
    <th>Before</th>
    <th>After</th>
    <tr>
        <td>Replace all ' with "</td>
        <td>"kotlin-android"</td>
        <td>'kotlin-android'</td>
    </tr>
    <tr>
        <td>Replace "def " with "val "</td>
        <td>val appcompat = "1.0.0"</td>
        <td>def appcompat = "1.0.0"</td>
    </tr>
    <tr>
        <td>Convert plugins</td>
        <td>apply(plugin = "kotlin-kapt")</td>
        <td>apply plugin: "kotlin-kapt"</td>
    </tr>
    <tr>
        <td>Add ( ) to dependencies</td>
        <td>implementation ":epoxy"</td>
        <td>implementation(":epoxy")</td>
    </tr>
    <tr>
        <td>Convert Maven</td>
        <td>maven("https://jitpack.io")</td>
        <td>maven { url "https://jitpack.io" }</td>
    </tr>
    <tr>
        <td>Convert Sdk Version</td>
        <td>compileSdkVersion(28)</td>
        <td>compileSdkVersion 28</td>
    </tr>
    <tr>
        <td>Convert Version Code</td>
        <td>versionCode = 4</td>
        <td>versionCode 4</td>
    </tr>
    <tr>
        <td>Convert Build Types</td>
        <td>isDebuggable = true</td>
        <td>debuggable true</td>
    </tr>
    <tr>
        <td>Convert proguardFiles</td>
        <td>setProguardFiles(listOf(getDef..., "...")</td>
        <td>proguardFiles getDef..., "..."</td>
    </tr>
    <tr>
        <td>Convert sourceCompatibility</td>
        <td>sourceCompatibility = JavaVersion.VERSION_1_8</td>
        <td>sourceCompatibility = "1.8"</td>
    </tr>
    <tr>
        <td>Convert androidExtensions</td>
        <td>androidExtensions { isExperimental = true }</td>
        <td>androidExtensions { experimental = true }</td>
    </tr>
    <tr>
        <td>Convert include</td>
        <td>include(":app", ":diffutils")</td>
        <td>include ":app", ":diffutils"</td>
    </tr>
    <tr>
        <td>Convert signingConfigs</td>
        <td>signingConfigs { register("debug") { ... } }</td>
        <td>signingConfigs { debug { ... } }</td>
    </tr>
    <tr>
        <td>Convert buildTypes</td>
        <td>buildTypes { named("debug") { ... } })</td>
        <td>buildTypes { debug { ... } }</td>
    </tr>
    <tr>
        <td>Convert classpath.exclude</td>
        <td>configurations.classpath { exclude(group = "...lombok") }</td>
        <td>configurations.classpath.exclude group: '...lombok'</td>
    </tr>
    <tr>
        <td>Kt dependencies (1/3)</td>
        <td>kotlin("gradle-plugin", version = "$kt_v")</td>
        <td>"org.jetbrains.kotlin:kotlin-gradle-plugin:$kt_v"</td>
    </tr>
    <tr>
        <td>Kt dependencies (2/3)</td>
        <td>kotlin("stdlib", KotlinCompilerVersion.VERSION)</td>
        <td>"org.jetbrains.kotlin:kotlin-stdlib:$kt_v"</td>
    </tr>
    <tr>
        <td>Kt dependencies (3/3)</td>
        <td>kotlin("reflect")</td>
        <td>"org.jetbrains.kotlin:kotlin-reflect"</td>
    </tr>
    <tr>
        <td>Convert signingConfig</td>
        <td>signingConfig = signingConfigs.getByName("release")</td>
        <td>signingConfig signingConfigs.release</td>
    </tr>
    <tr>
        <td>Convert extras</td>
        <td>extra.set("enableCrashlytics", false)</td>
        <td>ext.enableCrashlytics = false</td>
    </tr>
    <tr>
        <td>Convert plugins</td>
        <td>plugins { id(...) id(...) }</td>
        <td>apply(...) apply(...)</td>
    </tr>
    <tr>
        <td>Convert plugin ids</td>
        <td>id("io.gitlab.arturbosch.detekt") version "1.0"</td>
        <td>id "io.gitlab.arturbosch.detekt" version "1.0"</td>
    </tr>
    <tr>
        <td>Convert ":" to " ="</td>
        <td>testImpl(name = "junit", version = "4.12")</td>
        <td>testImpl(name: "junit", version: "4.12")</td>
    </tr>
</table>
