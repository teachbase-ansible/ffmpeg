Ansible role for FFmpeg
========

Installs FFMPEG from source code with the following libs:
- libfdk-aac
- libspeex
- libopus
- libvpx
- libtheora
- libvorbis
- libmp3lame
- x264
- yasm
- nasm

Based on [Official FFmpeg Compilation Guide](https://trac.ffmpeg.org/wiki/CompilationGuide)

Installation
--------------

`ansible-galaxy install teachbase-ansible.ffmpeg`

Role Variables
--------------

`defaults/main.yml`

| Name                        | Default Value | Description                                                      |
|-----------------------------|---------------|------------------------------------------------------------------|
| ffmpeg_source_dir           | /usr/local/src | Sources path                                                    |
| ffmpeg_build                | /usr/local/ffmpeg_build | Build path                                             |
| ffmpeg_bin_dir              | /usr/local/bin | Binaries path                                                   |
| ffmpeg_env                  | PKG_CONFIG_PATH: "{{ ffmpeg_build }}/lib/pkgconfig" | Environment vars           |
| ffmpeg_flags                | ... (see source) | FFMPEG compilation flags                                      |

Example Playbook
-------------------------

    - hosts: servers
      roles:
         - teachbase-ansible.ffmpeg
