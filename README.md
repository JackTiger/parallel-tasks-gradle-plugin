![](https://travis-ci.org/barryearles/parallel-tasks-gradle-plugin.svg)
# Parallel Task Execution Gradle Plugin

This plugin allows tasks that are defined within the same module to be executed in parallel.  It should not be confused with the [--parallel](https://github.com/gradle/gradle/blob/master/design-docs/done/parallel-project-execution.md "--parallel") option that allows tasks from separate projects in a decoupled multi-project build to be executed in parallel.

## Use Case

I needed the ability to run several servers concurrently to assist with development

## Usage

Add the dependency to your build script

	TODO

Apply the plugin

	apply plugin: 'parallel-tasks'

Configure the tasks that you wish to be executed in parallel

	task webpackDevServer << {
        // Start Webpack Dev Server
    }

    task browsersyncServer << {
        // Start Browsersync Server
    }

    parallelTasks {
        taskNames = [
            "browsersyncServer",
            "webpackDevServer",
            "bootRun"  // Task provided by "spring-boot" gradle plugin (e.g. apply plugin: 'spring-boot')
        ]
    }

## Building from Source

	./gradlew clean build
