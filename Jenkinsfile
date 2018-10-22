django('django') {
    currentBuild.result = "SUCCESS"

    try {

       stage('Test'){

         print "Checking if git is installed"

         sh 'git -v'

       }

       stage('Pull from repository'){

          sh './pullFromGit.sh'

       }

       stage('Build Docker Image'){

          sh './dockerBuild.sh'
       }

       stage('Deploy'){

         echo 'Push to Repo'
         sh './dockerPushToHeroku.sh'

       }

    }

    catch (err) {

        currentBuild.result = "FAILURE"

        echo 'Build or Deploy failure'
       
        throw err
    }

}