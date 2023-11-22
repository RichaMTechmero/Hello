# Uncomment the next line to define a global platform for your project
# platform :ios, '9.0'

target 'GithubActionProject1122' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!

  # Pods for GithubActionProject1122
  pod 'FirebaseCore'
  target 'GithubActionProject1122Tests' do
    inherit! :search_paths
    # Pods for testing
  end

  target 'GithubActionProject1122UITests' do
    # Pods for testing
  end

end

post_install do |installer|
  # ios deployment version
  installer.pods_project.targets.each do |t|
    t.build_configurations.each do |config|
      config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '13.0'
    end
  end

  # fix for xcode14 codesign for dependencies - remove after fix oficially
  installer.pods_project.targets.each do |target|
    if target.respond_to?(:product_type) and target.product_type == "com.apple.product-type.bundle"
      target.build_configurations.each do |config|
          config.build_settings['CODE_SIGNING_ALLOWED'] = 'NO'
          config.build_settings['CODE_SIGNING_REQUIRED'] = 'NO'
          config.build_settings['EXPANDED_CODE_SIGN_IDENTITY'] = ""
      end
    end
  end
end
