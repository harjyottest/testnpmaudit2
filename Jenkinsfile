#!/usr/bin/env groovy 

/*
 * This file bootstraps the codified Continuous Delivery pipeline for extensions of SAP solutions such as SAP S/4HANA.
 * The pipeline helps you to deliver software changes quickly and in a reliable manner.
 * A suitable Jenkins instance is required to run the pipeline.
 * More information on getting started with Continuous Delivery can be found here: https://sap.github.io/jenkins-library/
 */

@Library('piper-lib-os') _

node(){
  stage('Prepare')   {

      def output = sh script: "npm audit", returnStdout: true
      def summary = output.split("\n")[-1]

  }

  stage('Build')   {
        def output = sh script: "npm audit", returnStdout: true
        def summary = output.split("\n")[-1]
  }

  stage('Deploy')   {
      cloudFoundryDeploy script:this, deployTool:'mtaDeployPlugin'
  }
}