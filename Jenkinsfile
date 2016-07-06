echo 'starting jenkins build'

// Assign node with Label java
node('docker-maven-slave') { //
	// Check type of Node
	// env.PATH = "${tool 'Maven'}/bin:${env.PATH}"

	stage 'Checkout'

	// Checkout code
	git credentialsId: 'egb2016', url: 'https://github.com/DevSquadOrganization/Repo1.git'

	stage 'Build'
    // Maven  build
    sh 'mvn clean org.jacoco:jacoco-maven-plugin:0.7.2.201409121644:prepare-agent install -U'
    // Archive JUnitResults
    // step([$class: 'JUnitResultArchiver', testResults: 'target/surefire-reports/TEST-com.optum.ocd.sonarservice*.xml'])


}

echo 'Build Completed'
