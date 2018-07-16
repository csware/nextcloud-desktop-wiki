## Step by step instructions for Visual Studio Community 2017 15.7.5

- Click with the right button on the desktop folder and pick to open on Visual Studio:

[[https://raw.githubusercontent.com/wiki/nextcloud/desktop/images/vc_opens_desktop.png|alt=Open cmake project on Visual Studio]]

- Open the [CMakeSettings.json](https://blogs.msdn.microsoft.com/vcblog/2017/08/14/cmake-support-in-visual-studio-customizing-your-environment/):

[[https://raw.githubusercontent.com/wiki/nextcloud/desktop/images/vs_open_cmake_json.png|alt=Open CMakeSettings.json]]

- Edit with the correct options - change the generator and disable Shibboleth:

[[https://raw.githubusercontent.com/wiki/nextcloud/desktop/images/vs_json_conf.png|alt=Edit CMakeSettings.json]]

- Pick the configuration you want to run:

[[https://raw.githubusercontent.com/wiki/nextcloud/desktop/images/vs_pick_debug.png|alt=Pick Debug or Release]]

- Build it:

[[https://raw.githubusercontent.com/wiki/nextcloud/desktop/images/vs_build_options.png|alt=Build Debug or Release]]

- Run the selected configuration:

[[https://raw.githubusercontent.com/wiki/nextcloud/desktop/images/vs_start_debug.png|alt=Run Debug or Release]]