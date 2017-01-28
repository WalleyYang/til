# Install Maven OS X (10.11.5)

```bash
# Set JAVA_HOME if it has not been set
$ export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_45.jdk/Contents/Home

# Extract to opt directory and set the path
$ export PATH=/opt/apache-maven-3.3.9/bin:$PATH
```

# Command Line
```bash
# Generate structure
$ mvn archetype:generate

# Clean project
$ mvn clean
```

# Build Lifecycle Phases
```bash
# Validate project is correct and all necessary information is available
validate

# Compile source code of the project
compile

# Compile source code using unit testing framework
test

# Take compiled source code and package it in its distributable format, such as JAR
package

# Run any checks on results of integration tests to ensure quality criteria are met
verify

# Install the package into the local repository
install

# Done in the build environment, copies final package to the remote repository
deploy
```
