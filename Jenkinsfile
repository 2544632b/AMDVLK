#!/usr/bin/env groovy

/**
 * Pipeline for building and upload deb package of AMDVLK
 *
 * Build parameters:
 *      @githubToken: token to access github
 */

pipeline {
    agent none
    stages {
        stage("BuildPackage") {
            agent { label "jacob-jenkins" }
            steps {
                runScript()
            }
        }
    }
}

def runScript() {
    def workDir = "${WORKSPACE}"

    sh "python ${WORKSPACE}/bin/amdvlk_build_deb_from_tag.py -w ${WORKSPACE} -a ${githubToken}"
}
