Visual Studio Code Configuration for ESP-IDF Projects
=====================================================

This is a simple but nicely working .vscode configuration for your ESP-IDF projects.

In the meantime, this configuration was not working for me anymore but this was probably due to an update of the [vscode-cpptools](https://github.com/Microsoft/vscode-cpptools)?!

Setup
=====

All you have to do is to add this repository as a Git submodule to your project:

```
git submodule add https://github.com/pathob/.vscode-esp32.git .vscode
```

Make sure that you have configured the `IDF_PATH` environment variable as described here:
[Add IDF_PATH to User Profile](https://docs.espressif.com/projects/esp-idf/en/latest/get-started/add-idf_path-to-profile.html)

Furthermore, create another environment variable `XTENSA_ESP32_ELF_PATH` that points to your `xtensa-esp32-elf` directory.

On Linux, this could look like this:

```
export ESP_PATH=/path/to/esp/tools

export IDF_PATH=${ESP_PATH}/esp-idf
export PATH="$PATH:${IDF_PATH}/tools"

export XTENSA_ESP32_ELF_PATH=${ESP_PATH}/xtensa-esp32-elf
export PATH=${PATH}:${XTENSA_ESP32_ELF_PATH}/bin
```

Issues / Future Work
====================

It should be possible to improve the includes by providing a `compile_commands.json` file as described here:
[How to specify the include paths?](https://github.com/Microsoft/vscode-cpptools/blob/master/Documentation/Getting%20started%20with%20IntelliSense%20configuration.md#how-to-specify-the-include-paths)
But this probably requires CMake as the build tool (which will be mandatory in the future anyway).

Feel free to contribute via pull request if you made any generic improvements.

