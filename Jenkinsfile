pipeline {
	agent any
	
	stages {
		stage('Setup') {
			steps {
				sh "/Users/Marie/Desktop/install.sh"
			}
		}

		stage('Test') {
			parallel {
				stage('Android') {
					steps {s
						sh "cd /Users/Marie/Desktop/test"
						+ "&& parallel_calabash -a /Users/admin/Desktop/test/prebuilt/APP_ANDROID/FDJ-android-recette-1.4.0.apk -o'-r features/android' /features --concurrent"
					}
				}
				stage('IOS') {
					steps {
						sh "cd /Users/Marie/Desktop/test"
						+ "&& parallel_calabash --app fr.fdj.fdj.development --ios_config ~/.parallel_calabash.iphoneos -o'-r features/ios' /features --concurrent"
					}
				}
				
			}
		}
	}
}