# Node-Red[
    {
        "id": "f5eeaac6.768708",
        "type": "inject",
        "z": "b10e8d04.522b1",
        "name": "",
        "topic": "",
        "payload": "",
        "payloadType": "date",
        "repeat": "5",
        "crontab": "",
        "once": true,
        "x": 142,
        "y": 207,
        "wires": [
            [
                "510bfed9.00172"
            ]
        ]
    },
    {
        "id": "510bfed9.00172",
        "type": "function",
        "z": "b10e8d04.522b1",
        "name": "Payload",
        "func": "msg.headers={\n    deviceKey: \"wJIIZlJuqNwZUT7q\"\n    };\n    \nmsg.payload= \"Temperature,,25.3\"    \nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 304,
        "y": 280,
        "wires": [
            [
                "e200fcfb.45593"
            ]
        ]
    },
    {
        "id": "e200fcfb.45593",
        "type": "http request",
        "z": "b10e8d04.522b1",
        "name": "",
        "method": "GET",
        "ret": "txt",
        "url": "https://api.mediatek.com/mcs/v2/devices/DTD1XVUc/datapoints.csv",
        "tls": "",
        "x": 470,
        "y": 280,
        "wires": [
            [
                "dfb9746b.271cb8",
                "7aae526a.1d1e3c"
            ]
        ]
    },
    {
        "id": "dfb9746b.271cb8",
        "type": "http response",
        "z": "b10e8d04.522b1",
        "name": "",
        "statusCode": "",
        "headers": {},
        "x": 650,
        "y": 280,
        "wires": []
    },
    {
        "id": "7aae526a.1d1e3c",
        "type": "debug",
        "z": "b10e8d04.522b1",
        "name": "",
        "active": true,
        "console": "false",
        "complete": "payload",
        "x": 675,
        "y": 368,
        "wires": []
    }
]
