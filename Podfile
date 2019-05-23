source 'https://github.com/CocoaPods/Specs.git'

use_frameworks!

project 'Condulet'

abstract_target "All Targets" do
    target "Condulet" do
        platform :ios, '10.0'
        pod 'SwiftProtobuf'
    end
    target "ConduletTests" do
        platform :ios, '10.0'
        pod 'Quick'
        pod 'Nimble'
        pod 'Mockingjay'
    end
end

post_install do |installer|
    installer.pods_project.targets.each do |target|
      target.build_configurations.each do |config|
        if target.name == 'SwiftProtobuf'
          config.build_settings['SWIFT_VERSION'] = '5'
        else
          config.build_settings['SWIFT_VERSION'] = '4.2'
        end
        config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '10.0'
      end
    end
end
