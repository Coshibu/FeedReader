owncloud_resources = gnome.compile_resources(
  'owncloud_res',
  'owncloud.gresource.xml'
)

shared_library(
  'owncloud',
  [
    'OwncloudNewsAPI.vala',
    'OwncloudNewsInterface.vala',
    'OwncloudNewsUtils.vala',
    'OwncloudNewsMessage.vala'
  ],
  owncloud_resources,
  c_args: c_args,
  vala_args: vala_args,
  dependencies: [
    libpeas,
    libgd,
    gtk,
    gee,
    libsecret,
    sqlite3,
    libsoup,
    libxml,
    json_glib,
    webkit2gtk
  ],
  link_with: [
    feedreader_lib
  ],
  install: true,
  install_dir: BACKEND_PLUGINS_DIR,
  include_directories: include_directories('../../..')
)

install_data(
  [
    'org.gnome.feedreader.owncloud.gschema.xml'
  ],
  install_dir: join_paths(SHARE_DIR, 'glib-2.0/schemas')
)

install_data(
  [
    'owncloud.plugin'
  ],
  install_dir: BACKEND_PLUGINS_DIR
)
