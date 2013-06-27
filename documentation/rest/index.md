---
layout: documentation
---
Sometimes it's useful to interact with RoboHydra from an external
program. The typical usecase would be setting an appropriate scenario
before running a test, but there are other, interesting
possibilities. For that reason, RoboHydra offers a simple REST API to
gather information and change the current state (attach/detach heads,
start/stop scenarios).

Format
------

For now, all URLs in the API return always JSON, and don't pay any
attention to the `Accept` headers. See each URL for specific examples.

Plugins
-------

    http://localhost:3000/robohydra-admin/rest/plugins

This call gives you the list of loaded plugins, together the full
information for each plugin's heads and scenarios. Example output
(reformatted for readability):

    {
        "plugins": [
            {
                "heads": [], 
                "name": "logger", 
                "scenarios": []
            }, 
            {
                "heads": [
                    {
                        "attached": true, 
                        "name": "language-detection", 
                        "plugin": "simple-i18n"
                    }, 
                    {
                        "attached": true, 
                        "name": "plain-fileserver", 
                        "plugin": "simple-i18n"
                    }
                ], 
                "name": "simple-i18n", 
                "scenarios": []
            }
        ]
    }

