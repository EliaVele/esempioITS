pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Run if prova.py changed') {
            when {
                changeset pattern: "prova.py", comparator: "GLOB"//viene considerata qualsiasi modifica al file prova.py
            }
            steps {
                echo "prova.py è stato modificato. Eseguo la pipeline."
                sh "python3 prova.py"//il file prova.py deve esistere all'interno del branch Git a cui mi collego con la configurazione dell'SCM
            }
        }
    }
}
