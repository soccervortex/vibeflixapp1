require_relative './node_modules/@capacitor/ios/scripts/pods_helpers'

platform :ios, '14.0'
use_frameworks!

# workaround to avoid Xcode caching of Pods that requires
# Product -> Clean Build Folder after new Cordova plugins installed
# Requires CocoaPods 1.6 or newer
install! 'cocoapods', :disable_input_output_paths => true
warn_for_unused_master_specs_repo => false
def capacitor_pods
  pod 'Capacitor', :path => './node_modules/@capacitor/ios'
  pod 'CapacitorCordova', :path => './node_modules/@capacitor/ios'
end

target 'App' do
  capacitor_pods
  # Add your Pods here
end

post_install do |installer|
  assertDeploymentTarget(installer)
end
