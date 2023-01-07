plugin "cocoapods-binary-cache"

config_cocoapods_binary_cache(
  cache_repo: {
    "default" => {
      # "remote" => "https://github.com/onezerocompany/pods-cache.git",
      "remote" => "git@github.com:onezerocompany/pods-cache.git",
      "local" => "."
    }
  },
  device_build_enabled: true,
  xcframework: true,
)

platform :ios, '11.0'

# CocoaPods analytics sends network stats synchronously affecting flutter build latency.
ENV['COCOAPODS_DISABLE_STATS'] = 'true'

target 'Pod Project' do

  use_frameworks!
  use_modular_headers!

  pod 'AppAuth', '~> 1.6.0', :binary => true
  pod 'BoringSSL-GRPC', '~> 0.0.24', :binary => true
  pod 'FirebaseABTesting', '~> 10.3.0', :binary => true
  pod 'FirebaseAnalytics', '~> 10.3.0', :binary => true
  pod 'FirebaseAppCheckInterop', '~> 10.3.0', :binary => true
  pod 'FirebaseAuth', '~> 10.3.0', :binary => true
  pod 'FirebaseAuthInterop', '~> 10.3.0', :binary => true
  pod 'FirebaseCoreExtension', '~> 10.3.0', :binary => true
  pod 'FirebaseCore', '~> 10.3.0', :binary => true
  pod 'FirebaseCoreInternal', '~> 10.3.0', :binary => true
  pod 'FirebaseDynamicLinks', '~> 10.3.0', :binary => true
  pod 'FirebaseFirestore', '~> 10.3.0', :binary => true
  pod 'FirebaseInstallations', '~> 10.3.0', :binary => true
  pod 'FirebaseMessaging', '~> 10.3.0', :binary => true
  pod 'FirebaseMessagingInterop', '~> 10.3.0', :binary => true
  pod 'FirebasePerformance', '~> 10.3.0', :binary => true
  pod 'FirebaseRemoteConfig', '~> 10.3.0', :binary => true
  pod 'FirebaseSharedSwift', '~> 10.3.0', :binary => true
  pod 'GoogleAppMeasurement', '~> 10.3.0', :binary => true
  pod 'GoogleDataTransport', '~> 9.2.0', :binary => true
  pod 'GoogleSignIn', '~> 6.2.4', :binary => true
  pod 'GoogleUtilities', '~> 7.10.0', :binary => true
  pod 'Mapbox-iOS-SDK', '~> 6.4.1', :binary => true
  pod 'MapboxAnnotationExtension', '~> 0.0.1-beta.2', :binary => true
  pod 'MapboxMobileEvents', '~> 0.10.14', :binary => true

end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings.delete('IPHONEOS_DEPLOYMENT_TARGET')
    end
  end
  installer.pods_project.build_configurations.each do |config|
    config.build_settings["EXCLUDED_ARCHS[sdk=iphonesimulator*]"] = "arm64"
    config.build_settings["ONLY_ACTIVE_ARCH"] = "YES"
  end
end
