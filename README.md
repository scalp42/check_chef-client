# DESCRIPTION:

Nagios check for a host running chef-client as a service. Also comes with a restart-handler in case chef-client is dead.

# REQUIREMENTS:

You need to add Nagios master as a workstation in Chef, as it's using knife command to perform the check. Please note that the check is meant to be ran from the Nagios server (hence "localhost").
You also need to make sure that user "nagios" can ssh into the hosts failing.

# USAGE:

Edit your nagios configuration to include something like this :

	define service{
        	use generic-service
	        host_name localhost
	        service_description check_chef-client
	       	check_command check_chef-client
       		event_handler restart-chef-clients
	}

# TODO:

Too much stuff.

# LICENSE & AUTHOR:

Author:: Anthony Scalisi (scalisi.a@gmail.com)

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

	http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.