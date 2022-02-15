# descriptor_config.json
 "xapp_name": "qp",
        "version": "0.0.4",
        "containers": [
            {
                "name": "qp",
                "image": {
                    "registry": "nexus3.o-ran-sc.org:3333",
                    "name": "o-ran-sc/ric-app-qp",
                    "tag": "0.0.4"
                }
            }
        ],
        "messaging": {
            "ports": [
                {
                    "name": "rmr-data",
                    "container": "qp",
                    "port": 2510,
                    "rxMessages": ["TS_UE_LIST"],
                    "txMessages": ["TS_QOE_PREDICTION"],
                    "policies": [],
                    "description": "rmr receive data port for qp"
                },
                {
                    "name": "rmr-route",
                    "container": "qp",
                    "port": 2147,
                    "description": "rmr route port for qp"
                }
            ]
        },
        "rmr": {
            "protPort": "tcp:4562",
            "maxSize": 2072,
            "numWorkers": 1,
            "rxMessages": ["TS_UE_LIST"],
            "txMessages": ["TS_QOE_PREDICTION"],
            "policies": []
        }
}
