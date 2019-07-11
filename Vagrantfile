# Freedom Cloud. Management code for a self-hosted file server.
# Copyright (C) 2019  Kris Lamoureux
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, version 3 of the License.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <https://www.gnu.org/licenses/>.
#
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # Debian Stable
  # Temporary box until debian/buster64 updates
  # https://lists.debian.org/debian-cloud/2019/07/msg00023.html
  config.vm.box = "krislamo/debian"

  # Disable default sync
  config.vm.synced_folder '.', '/vagrant', disabled: true

  # Get local IP and display
  config.vm.network :forwarded_port, guest: 80, host: 8080

  # Run Ansible
  config.vm.provision "ansible" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "testing.yml"
  end

end

