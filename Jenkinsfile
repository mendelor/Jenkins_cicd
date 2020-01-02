agent any
stages {
stage("Compile") {
steps {
sh "./gradlew compile.Java"
}
}
stage("Unit test") {
steps {
sh "./gradlew test"
}
}
}
}
