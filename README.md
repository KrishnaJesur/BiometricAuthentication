# BiometricAuthentication

Usage

val promptInfo = androidx.biometric.BiometricPrompt.PromptInfo.Builder()
            .setTitle("Set the title to display.")
            .setSubtitle("Set the subtitle to display.")
            .setDescription("Set the description to display")
            .setNegativeButtonText("Negative Button")
            .build()


Biometric CallBack has the Following Methods :

val executor = Executors.newSingleThreadExecutor()
        val activity: FragmentActivity = this // reference to activity
        val biometricPrompt =
            androidx.biometric.BiometricPrompt(
                activity,
                executor,
                object : androidx.biometric.BiometricPrompt.AuthenticationCallback() {

                    override fun onAuthenticationError(errorCode: Int, errString: CharSequence) {
                        super.onAuthenticationError(errorCode, errString)
                        if (errorCode == androidx.biometric.BiometricPrompt.ERROR_NEGATIVE_BUTTON) {
                            // user clicked negative button
                        } else {
//                    TODO("Called when an unrecoverable error has been encountered and the operation is complete.")
                        }
                    }

                    override fun onAuthenticationSucceeded(result: androidx.biometric.BiometricPrompt.AuthenticationResult) {
                        super.onAuthenticationSucceeded(result)
//                    TODO("Called when a biometric is recognized.")
                        Log.d("success", "")
                    }

                    override fun onAuthenticationFailed() {
                        super.onAuthenticationFailed()
//                    TODO("Called when a biometric is valid but not recognized.")
                    }

                })
