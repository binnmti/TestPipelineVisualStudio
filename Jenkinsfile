node {
	stage 'Checkout'
		checkout scm

	stage 'Build'
		bat 'nuget restore TestPipelineVisualStudio.sln'
		bat "\"${tool 'MSBuild14'}msbuild.exe\" TestPipelineVisualStudio.sln /p:Configuration=Release /p:Platform=Any CPU /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"

	stage 'Archive'
		archive 'bin/Release/**'

}