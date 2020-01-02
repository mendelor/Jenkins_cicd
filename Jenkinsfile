agent any
stages {
stage("Compile") {
steps {
sh "./gradlew compile.Java1"
}
}
stage("Unit test") {
steps {
sh "./gradlew test"
}
}
}

