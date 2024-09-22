#source 'https://github.com/CocoaPods/Specs'
#source 'https://mirrors.tuna.tsinghua.edu.cn/git/CocoaPods/Specs.git'

# Uncomment the next line to define a global platform for your project
platform :ios, '14.0'

target 'FastAI' do
  # Uncomment the next line if you're using Swift or would like to use dynamic frameworks
  use_frameworks!

pod "OpenCV"
pod 'Masonry'
pod 'ffmpeg-kit-ios-full', '~> 6.0'
pod "onnxruntime-objc"
pod 'FLEX', :configurations => ['Debug']

end
post_install do |installer|
  installer.generated_projects.each do |project|
    project.targets.each do |target|
        target.build_configurations.each do |config|
          config.build_settings["EXCLUDED_ARCHS[sdk=iphonesimulator*]"] = "arm64"
          if config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'].to_f < 14.0
              config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '14.0'
          end
        end
    end
  end
end
