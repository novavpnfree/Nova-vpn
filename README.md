#profile-title:⚡ NOVA VPN⚡ 

#profile-update-interval: 1

#profile-description: nova vpn 😎 автообновление каждый час ❤️‍🩹


{
  "api": {
    "services": [
      "StatsService"
    ],
    "tag": "api"
  },
  "burstObservatory": {
    "pingConfig": {
      "connectivity": "https:\/\/browser.yandex.ru\/generate_204",
      "destination": "https:\/\/www.google.com",
      "httpMethod": "GET",
      "interval": "15s",
      "sampling": 4,
      "timeout": "2s"
    },
    "subjectSelector": [
      "proxy"
    ]
  },
  "dns": {
    "disableCache": false,
    "hosts": {
      "lkfl2.nalog.ru": [
        "213.24.64.175",
        "213.24.64.17"
      ],
      "lknpd.nalog.ru": [
        "213.24.64.181"
      ],
      "safe.dot.dns.yandex.net": [
        "77.88.8.88",
        "77.88.8.2",
        "2a02:6b8::feed:bad",
        "2a02:6b8:0:1::feed:bad"
      ],
      "security.cloudflare-dns.com": [
        "1.1.1.2",
        "1.0.0.2",
        "2606:4700:4700::1112",
        "2606:4700:4700::1002"
      ]
    },
    "queryStrategy": "UseIPv4",
    "serveExpiredTTL": 10,
    "serveStale": true,
    "servers": [
      "https:\/\/security.cloudflare-dns.com\/dns-query",
      "https+local:\/\/security.cloudflare-dns.com\/dns-query",
      "https+local:\/\/dns.google\/dns-query",
      "tcp+local:\/\/77.88.8.88:53"
    ],
    "useSystemHosts": true
  },
  "inbounds": [
    {
      "listen": "127.0.0.1",
      "port": 10808,
      "protocol": "socks",
      "settings": {
        "auth": "noauth",
        "udp": true,
        "userLevel": 8
      },
      "sniffing": {
        "destOverride": [
          "http",
          "tls",
          "quic"
        ],
        "enabled": true,
        "routeOnly": true
      },
      "tag": "socks"
    },
    {
      "listen": "127.0.0.1",
      "port": 10809,
      "protocol": "http",
      "settings": {
        "userLevel": 8
      },
      "sniffing": {
        "destOverride": [
          "http",
          "tls",
          "quic"
        ],
        "enabled": true,
        "routeOnly": true
      },
      "tag": "http"
    },
    {
      "listen": "127.0.0.1",
      "port": 11111,
      "protocol": "dokodemo-door",
      "settings": {
        "address": "127.0.0.1"
      },
      "tag": "metrics_in"
    },
    {
      "listen": "127.0.0.1",
      "port": 10085,
      "protocol": "dokodemo-door",
      "settings": {
        "address": "127.0.0.1"
      },
      "tag": "api_in"
    }
  ],
  "log": {
    "loglevel": "warning"
  },
  "meta": null,
  "metrics": {
    "tag": "metrics_out"
  },
  "outbounds": [
    {
      "tag": "proxy-1",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "109.172.87.68",
            "port": 443,
            "users": [
              {
                "id": "f4b08bf1-d9bd-4755-aa88-ba922282c608",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "rusamicro67.richhoodfoc.com",
          "fingerprint": "firefox",
          "alpn": [
            "h2"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/v2\/telemetry\/c3a474d77a",
          "mode": "auto",
          "host": "rusamicro67.richhoodfoc.com"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-2",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "45.146.166.64",
            "port": 2083,
            "users": [
              {
                "id": "fb721937-6284-0019-9cbd-c3ba2cb66b4a",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "cdn.mornismp.ru",
          "fingerprint": "firefox"
        },
        "xhttpSettings": {
          "path": "\/transport\/xhttp",
          "host": "45.146.166.64"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-3",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "5.23.53.44",
            "port": 443,
            "users": [
              {
                "id": "62713f49-9138-410b-b249-7a53c843c5d2",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "ws",
        "security": "tls",
        "tlsSettings": {
          "serverName": "baza221.wba-pn.ru",
          "fingerprint": "firefox"
        },
        "wsSettings": {
          "path": "\/"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-4",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "85.8.201.247",
            "port": 2083,
            "users": [
              {
                "id": "fb721937-6284-0002-9cbd-c3ba2cb66b4a",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "cdn.mornismp.ru",
          "fingerprint": "firefox"
        },
        "xhttpSettings": {
          "path": "\/transport\/xhttp",
          "host": "85.8.201.247"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-5",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "178.177.17.206",
            "port": 8446,
            "users": [
              {
                "id": "1bc72df2-f188-4bd1-8c9f-395dbb5f5cf7",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "178.177.17.206",
          "fingerprint": "firefox"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-6",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "178.177.17.206",
            "port": 8446,
            "users": [
              {
                "id": "1bc72df2-f188-4bd1-8c9f-395dbb5f5cf7",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "178.177.17.206",
          "fingerprint": "firefox"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-7",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "185.171.82.185",
            "port": 12445,
            "users": [
              {
                "id": "e81a8f30-23b9-5b7a-90d9-ec040f682220",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "tia.kunisosi.bid",
          "fingerprint": "firefox",
          "publicKey": "G4eNHGX_1QXsdr-GfxHBEscXmIYLncUW82i4FUFvY2k",
          "shortId": "70a75d07aa1d1c04"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-8",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "178.236.254.84",
            "port": 8443,
            "users": [
              {
                "id": "1ade7da3-edbe-4e1d-acd3-9738379a0dac",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "reality",
        "realitySettings": {
          "serverName": "cdn-plng.cahmes.space",
          "fingerprint": "firefox",
          "publicKey": "CfNBTIsftRSg56DcYqqFTug11Ff4IirfnbUAzyL6ZmE",
          "shortId": "39a5886e503ec5ab"
        },
        "xhttpSettings": {
          "path": "\/xhttp",
          "host": "178.236.254.84"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-9",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "195.78.48.157",
            "port": 8443,
            "users": [
              {
                "id": "1ade7da3-edbe-4e1d-acd3-9738379a0dac",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "reality",
        "realitySettings": {
          "serverName": "cdn-fr.cahmes.space",
          "fingerprint": "firefox",
          "publicKey": "x4SMsuhbmd22EHfnfxPZfIQs2BuHT2mKFvL6UwSMWS0",
          "shortId": "5c3b5015fc2885e4"
        },
        "xhttpSettings": {
          "path": "\/xhttp",
          "host": "195.78.48.157"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-10",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "178.236.254.81",
            "port": 8443,
            "users": [
              {
                "id": "1ade7da3-edbe-4e1d-acd3-9738379a0dac",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "reality",
        "realitySettings": {
          "serverName": "cdn-es.cahmes.space",
          "fingerprint": "firefox",
          "publicKey": "dSH20qQm9nyDIN1gI1KyUjtVOilHh0wG8t-Xw1iz638",
          "shortId": "01f0a0809d05552b"
        },
        "xhttpSettings": {
          "path": "\/xhttp",
          "host": "178.236.254.81"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-11",
      "protocol": "hysteria",
      "settings": {
        "version": 2,
        "address": "193.124.66.172",
        "port": 443
      },
      "streamSettings": {
        "network": "hysteria",
        "security": "tls",
        "method": "hysteria",
        "tlsSettings": {
          "serverName": "lv.0000000000000.space"
        },
        "hysteriaSettings": {
          "version": 2,
          "auth": "2444df7f-4a0c-45bd-9c62-25a7ff8c4dba"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-12",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "82.202.182.32",
            "port": 5269,
            "users": [
              {
                "id": "0d4807a7-260b-4d66-a71e-5e793c46c66e",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "max.ru",
          "fingerprint": "firefox",
          "publicKey": "meI7RA9FgxL1yjJsbJBehEKoB2Z1ra4hyYJso9qtmFA",
          "shortId": "4b198dc3bfffb7af"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-13",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "89.223.17.67",
            "port": 443,
            "users": [
              {
                "id": "5db72264-1d45-0068-8f7e-d1574b43008e",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "nohope-67-s4.mcdeliver.ru",
          "fingerprint": "firefox",
          "publicKey": "Aj6Lfc0JKKROX46eHAQHlzrNpOTY9CKp7BcVj9cw8Ag",
          "shortId": "75f8575e5396a2fe"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-14",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "185.231.204.70",
            "port": 8443,
            "users": [
              {
                "id": "318d9cc0-248f-4f44-b79a-1ba4fda95c08",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "reality",
        "realitySettings": {
          "serverName": "www.aegon.com",
          "fingerprint": "firefox",
          "publicKey": "cj560j1TzKXUTD1UjZqPWGroeUtVc4CaIamhzbcxx14",
          "shortId": "ab2ba1fb41ca9692"
        },
        "xhttpSettings": {
          "path": "\/23469c1d080089734bba4416",
          "host": "185.231.204.70"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-15",
      "protocol": "hysteria",
      "settings": {
        "version": 2,
        "address": "193.124.66.172",
        "port": 443
      },
      "streamSettings": {
        "network": "hysteria",
        "security": "tls",
        "method": "hysteria",
        "tlsSettings": {
          "serverName": "lv.0000000000000.space",
          "alpn": [
            "h3"
          ]
        },
        "hysteriaSettings": {
          "version": 2,
          "auth": "2444df7f-4a0c-45bd-9c62-25a7ff8c4dba"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-16",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "api.setevoypriliv.cc",
            "port": 443,
            "users": [
              {
                "id": "2a7bf1d0-c4ef-43a6-b62a-22821db65b5e",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "api.setevoypriliv.cc",
          "fingerprint": "safari",
          "publicKey": "r5WB5FnSCt4eeBC1FJMfkWHbzsMuabo0Rc6wuAhlZUs",
          "shortId": "a8"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-17",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "almanac.filnex.baby",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "grpc",
        "security": "tls",
        "tlsSettings": {
          "serverName": "mossglade.merlano.monster",
          "fingerprint": "firefox",
          "alpn": [
            "h2"
          ]
        },
        "grpcSettings": {
          "serviceName": "glush.de1.v1",
          "authority": "almanac.filnex.baby"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-18",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "harbor.gerqix.online",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "ws",
        "security": "tls",
        "tlsSettings": {
          "serverName": "moorhen.gerqix.online",
          "fingerprint": "firefox",
          "alpn": [
            "http\/1.1"
          ]
        },
        "wsSettings": {
          "path": "\/api\/de1\/stream"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-19",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "sunfield.moltex.click",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "fennel.moltex.click",
          "fingerprint": "firefox",
          "alpn": [
            "h2",
            "http\/1.1"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/de1\/sync",
          "mode": "auto",
          "host": "sunfield.moltex.click"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-20",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "pebble.gerqix.online",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "grpc",
        "security": "tls",
        "tlsSettings": {
          "serverName": "windlass.gerqix.online",
          "fingerprint": "firefox",
          "alpn": [
            "h2"
          ]
        },
        "grpcSettings": {
          "serviceName": "glush.de2.v1",
          "authority": "pebble.gerqix.online"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-21",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "bayleaf.elvano.website",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "bayleaf.elvano.website",
          "fingerprint": "firefox",
          "alpn": [
            "h2",
            "http\/1.1"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/de3\/sync",
          "mode": "auto",
          "host": "bayleaf.elvano.website"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-22",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "alderbloom.gerqix.online",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "inlet.gerqix.online",
          "fingerprint": "firefox",
          "alpn": [
            "h2"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/de4\/preview\/",
          "mode": "packet-up",
          "host": "inlet.gerqix.online"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-23",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "sundial.filnex.baby",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "ws",
        "security": "tls",
        "tlsSettings": {
          "serverName": "silverfen.elvano.website",
          "fingerprint": "firefox",
          "alpn": [
            "http\/1.1"
          ]
        },
        "wsSettings": {
          "path": "\/api\/de4\/stream"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-24",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "mintleaf.moltex.click",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "ws",
        "security": "tls",
        "tlsSettings": {
          "serverName": "mintleaf.moltex.click",
          "fingerprint": "firefox",
          "alpn": [
            "http\/1.1"
          ]
        },
        "wsSettings": {
          "path": "\/api\/de4\/stream"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-25",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "api.videodolina.cc",
            "port": 443,
            "users": [
              {
                "id": "2a7bf1d0-c4ef-43a6-b62a-22821db65b5e",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "api.videodolina.cc",
          "fingerprint": "firefox",
          "publicKey": "r5WB5FnSCt4eeBC1FJMfkWHbzsMuabo0Rc6wuAhlZUs",
          "shortId": "a8"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-26",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "cz-next.mediastvor.cc",
            "port": 443,
            "users": [
              {
                "id": "2a7bf1d0-c4ef-43a6-b62a-22821db65b5e",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "grpc",
        "security": "tls",
        "tlsSettings": {
          "serverName": "cz-next.mediastvor.cc",
          "fingerprint": "firefox",
          "alpn": [
            "h2"
          ]
        },
        "grpcSettings": {
          "serviceName": "r7Kp4mN9tQ2v",
          "authority": "cz-next.mediastvor.cc"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-27",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "lagoon.gerqix.online",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "ws",
        "security": "tls",
        "tlsSettings": {
          "serverName": "lagoon.gerqix.online",
          "fingerprint": "firefox",
          "alpn": [
            "http\/1.1"
          ]
        },
        "wsSettings": {
          "path": "\/api\/de5\/stream"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-28",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "wildflower.elvano.website",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "wildflower.elvano.website",
          "fingerprint": "firefox",
          "alpn": [
            "h2",
            "http\/1.1"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/de5\/sync",
          "mode": "auto",
          "host": "wildflower.elvano.website"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-29",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "stonecrop.merlano.monster",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "paperbirch.merlano.monster",
          "fingerprint": "firefox",
          "alpn": [
            "h2"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/de5\/preview\/",
          "mode": "packet-up",
          "host": "paperbirch.merlano.monster"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-30",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "gesso.merlano.monster",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "gesso.merlano.monster",
          "fingerprint": "firefox",
          "alpn": [
            "h2",
            "http\/1.1"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/de5\/sync",
          "mode": "auto",
          "host": "gesso.merlano.monster"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-31",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "cobblestone.merlano.monster",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "grpc",
        "security": "tls",
        "tlsSettings": {
          "serverName": "cobblestone.merlano.monster",
          "fingerprint": "firefox",
          "alpn": [
            "h2"
          ]
        },
        "grpcSettings": {
          "serviceName": "glush.de5.v1",
          "authority": "cobblestone.merlano.monster"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-32",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "seaglass.gerqix.online",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "seaglass.gerqix.online",
          "fingerprint": "firefox",
          "alpn": [
            "h2",
            "http\/1.1"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/de5\/sync",
          "mode": "auto",
          "host": "seaglass.gerqix.online"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-33",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "moonwort.gerqix.autos",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "birchmeadow.moltex.click",
          "fingerprint": "firefox",
          "alpn": [
            "h2"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/de6\/preview\/",
          "mode": "packet-up",
          "host": "birchmeadow.moltex.click"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-34",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "heatherfield.moltex.click",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "heatherfield.moltex.click",
          "fingerprint": "firefox",
          "alpn": [
            "h2",
            "http\/1.1"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/de6\/sync",
          "mode": "auto",
          "host": "heatherfield.moltex.click"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-35",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "copperplate.gerqix.online",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "copperplate.gerqix.online",
          "fingerprint": "firefox",
          "alpn": [
            "h2",
            "http\/1.1"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/de6\/sync",
          "mode": "auto",
          "host": "copperplate.gerqix.online"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-36",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "93.184.171.48",
            "port": 443,
            "users": [
              {
                "id": "9a9f167d-b461-466f-be50-f0ffd598a6f8",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "reality",
        "realitySettings": {
          "serverName": "srartsfoparts.store",
          "fingerprint": "firefox",
          "publicKey": "pF63V3JDoxSa9lMMKoXyxpjBJNqIsajj84LMXElvF1w",
          "shortId": "1205987ccd622887"
        },
        "xhttpSettings": {
          "path": "\/e90d4e998aad\/9d1d9b8b",
          "host": "srartsfoparts.store"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-37",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "31.77.138.211",
            "port": 8443,
            "users": [
              {
                "id": "55ba7b31-b0eb-4362-9c9b-fc53b0a53fab",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "reality",
        "realitySettings": {
          "serverName": "fi3.setlocation.top",
          "fingerprint": "firefox",
          "publicKey": "NCJNc0NqiDsOmTx8gJSzdNhWylbA6jSaQQYKW50HKzc",
          "shortId": "e4df5704c91b57bd"
        },
        "xhttpSettings": {
          "path": "\/4c6a7f5ff99a",
          "host": "31.77.138.211"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-38",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "31.76.8.195",
            "port": 443,
            "users": [
              {
                "id": "e894c08a-fecc-46f5-bf03-c95d0274c79d",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "lesson12.schoolpizorbz.xyz",
          "fingerprint": "firefox",
          "publicKey": "pFmgbfd2eUSmge-8f0dF7Yjo8OFaZWuZ3UWC7EXjwmg",
          "shortId": "ae3cdc4eca7374a8"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-39",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "31.76.21.252",
            "port": 443,
            "users": [
              {
                "id": "e894c08a-fecc-46f5-bf03-c95d0274c79d",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "lesson5.schoolpizorbz.xyz",
          "fingerprint": "firefox",
          "publicKey": "hkbj7k2VDqVjrwQLXhoWIgjUwGOKFJ9Y1gdCv2YGQik",
          "shortId": "190004e1840538bf"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-40",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "83.143.112.79",
            "port": 443,
            "users": [
              {
                "id": "e894c08a-fecc-46f5-bf03-c95d0274c79d",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "lesson10.schoolpizorbz.xyz",
          "fingerprint": "firefox",
          "publicKey": "IL8J51YZ8vzSpHXhvBNQUnACZjGKuSYLIDPLH5tZ4BA",
          "shortId": "c9899c71959d69e4"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-41",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "201.58.176.19",
            "port": 443,
            "users": [
              {
                "id": "e894c08a-fecc-46f5-bf03-c95d0274c79d",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "lesson9.schoolpizorbz.xyz",
          "fingerprint": "firefox",
          "publicKey": "LkXRut71yrHguNpmKfCrLITrAxk7amJiI2npZ4jRYx8",
          "shortId": "06df4d3e93672c24"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-42",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "45.33.75.68",
            "port": 443,
            "users": [
              {
                "id": "e3c6ed3a-b758-443c-aef1-112fa24019c3",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "amp-api-edge.apps.apple.com",
          "fingerprint": "firefox",
          "publicKey": "P-lHtRBeKWqfMfOoOF5dvfwEvU0geEkMuUXqFtF7yjQ",
          "shortId": "75beb3e297f4f26d"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-43",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "152.232.82.196",
            "port": 443,
            "users": [
              {
                "id": "2a7bf1d0-c4ef-43a6-b62a-22821db65b5e",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "api.videobereg.cc",
          "fingerprint": "firefox",
          "publicKey": "r5WB5FnSCt4eeBC1FJMfkWHbzsMuabo0Rc6wuAhlZUs",
          "shortId": "a8"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-44",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "170.114.45.6",
            "port": 443,
            "users": [
              {
                "id": "bc0f9e3a-6dad-42d5-b09f-dff4cdf57437",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "ws",
        "security": "tls",
        "tlsSettings": {
          "serverName": "googleapis.hmacreation.eu.cc",
          "fingerprint": "firefox"
        },
        "wsSettings": {
          "path": "\/",
          "headers": {
            "Host": "googleapis.hmacreation.eu.cc"
          }
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-45",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "45.88.162.111",
            "port": 8443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "turntable.elvano.website",
          "fingerprint": "firefox",
          "alpn": [
            "h2"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/preview\/",
          "mode": "packet-up",
          "host": "turntable.elvano.website"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-46",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "82.148.242.217",
            "port": 8443,
            "users": [
              {
                "id": "1ade7da3-edbe-4e1d-acd3-9738379a0dac",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "reality",
        "realitySettings": {
          "serverName": "cdn-plng.cahmes.space",
          "fingerprint": "firefox",
          "publicKey": "CfNBTIsftRSg56DcYqqFTug11Ff4IirfnbUAzyL6ZmE",
          "shortId": "39a5886e503ec5ab"
        },
        "xhttpSettings": {
          "path": "\/xhttp",
          "host": "82.148.242.217"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-47",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "kiln.elvano.website",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "kiln.elvano.website",
          "fingerprint": "firefox",
          "alpn": [
            "h2"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/preview\/",
          "mode": "packet-up",
          "host": "kiln.elvano.website"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-48",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "marginalia.gerqix.online",
            "port": 443,
            "users": [
              {
                "id": "749b1c56-e658-4bf5-94bd-5c3286a4aed1",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "marginalia.gerqix.online",
          "fingerprint": "firefox",
          "alpn": [
            "h2"
          ]
        },
        "xhttpSettings": {
          "path": "\/api\/preview\/",
          "mode": "packet-up",
          "host": "marginalia.gerqix.online"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-49",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "103.200.28.8",
            "port": 25812,
            "users": [
              {
                "id": "893fdb90-b1a1-4235-8f0d-56aac1cfde9e",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "grpc",
        "security": "reality",
        "realitySettings": {
          "serverName": "cz2.jetstoreapp.ru",
          "fingerprint": "firefox",
          "publicKey": "3g6uVc70EKi_XPzCTcZj_p77XJPpVUZvFNUPew4s0iU",
          "shortId": "8643513c64b7f35e"
        },
        "grpcSettings": {
          "serviceName": "7acacc2cc9d3"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-50",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "67.159.18.8",
            "port": 8443,
            "users": [
              {
                "id": "b58564f3-bcc4-4af9-8a47-7ad8039cba93",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "reality",
        "realitySettings": {
          "serverName": "www.novinky.cz",
          "fingerprint": "firefox",
          "publicKey": "T1ox3NAq2XpBQWzzHfro5L1ltDC6bv7ouFOYceuPmWQ",
          "shortId": "27f8050c"
        },
        "xhttpSettings": {
          "path": "\/api\/v6\/media\/02b73b0f\/",
          "host": "www.novinky.cz"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-51",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "82.118.19.153",
            "port": 443,
            "users": [
              {
                "id": "adcaa148-7c66-4282-a81a-99ec8afa029d",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "www.cloudflare.com",
          "fingerprint": "firefox",
          "publicKey": "Tiuy8om5Lk0pWL95-8LaFFTwH0vbURVMoOkaW9xGaiE",
          "shortId": "670ed9f350bd8ee0"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-52",
      "protocol": "shadowsocks",
      "settings": {
        "servers": [
          {
            "address": "8.209.80.17",
            "port": 443,
            "method": "2022-blake3-chacha20-poly1305",
            "password": "8yO3ANWefuuGs1lRKXECQA1FEhxlWFV2ppQMcBaZo5Y="
          }
        ]
      }
    },
    {
      "tag": "proxy-53",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "31.77.13.2",
            "port": 443,
            "users": [
              {
                "id": "e894c08a-fecc-46f5-bf03-c95d0274c79d",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "lesson67.schoolpizorbz.xyz",
          "fingerprint": "firefox",
          "publicKey": "I935dNNphFajETA83ynOilN61A0RRgzoZFF-6pZSu3Q",
          "shortId": "afd0d3b703f1ed70"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-54",
      "protocol": "hysteria",
      "settings": {
        "version": 2,
        "address": "94.249.225.65",
        "port": 443
      },
      "streamSettings": {
        "network": "hysteria",
        "security": "tls",
        "method": "hysteria",
        "tlsSettings": {
          "serverName": "nl1.nuvoryxdata.com"
        },
        "hysteriaSettings": {
          "version": 2,
          "auth": "81f705b5-9039-4adf-8671-783095bba0e8"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-55",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "87.121.112.39",
            "port": 443,
            "users": [
              {
                "id": "9a9f167d-b461-466f-be50-f0ffd598a6f8",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "reality",
        "realitySettings": {
          "serverName": "newbulg.live",
          "fingerprint": "firefox",
          "publicKey": "6d-S4tqmMUwh_O58kZAfLwbKB9e4FB2O_JbhjjhZ9zc",
          "shortId": "dbe40666c7960aa0"
        },
        "xhttpSettings": {
          "path": "\/e8f75cb41d80\/02ec0e47",
          "host": "newbulg.live"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-56",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "172.233.27.145",
            "port": 64552,
            "users": [
              {
                "id": "504b7143-71e0-4cf0-909b-5ff271bd03d6",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "www.cloudflare.com",
          "fingerprint": "firefox",
          "publicKey": "U7t4RFE9MSMtC-o1DoJ8pYzKMfgVpTg6ZhTTknBrVkU",
          "shortId": "1f2519bb96e5589c"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-57",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "83.141.79.239",
            "port": 8443,
            "users": [
              {
                "id": "1ade7da3-edbe-4e1d-acd3-9738379a0dac",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "reality",
        "realitySettings": {
          "serverName": "cdn-de.cahmes.space",
          "fingerprint": "firefox",
          "publicKey": "LP7yXSC50lHfxW-BuRQ3OLDBNncF2KVnMgVJuX9XR2w",
          "shortId": "35cd2022241da999"
        },
        "xhttpSettings": {
          "path": "\/xhttp",
          "host": "83.141.79.239"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-58",
      "protocol": "hysteria",
      "settings": {
        "version": 2,
        "address": "14.137.237.98",
        "port": 60001
      },
      "streamSettings": {
        "network": "hysteria",
        "security": "tls",
        "method": "hysteria",
        "tlsSettings": {
          "serverName": "hk01.kfc-520.com"
        },
        "hysteriaSettings": {
          "version": 2,
          "auth": "5ec96249-b753-317a-b065-b67ad66b8185"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-59",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "43.155.208.90",
            "port": 443,
            "users": [
              {
                "id": "21096a6d-88df-49c7-8882-d09e73b4da95",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "w.fugui.us",
          "fingerprint": "firefox",
          "publicKey": "J2yp_4F_8h4hHTntLf3URZRrdScOhOPOt1ct9LZJ5n4",
          "shortId": "9cab9354c40d5f68"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-60",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "196.198.111.189",
            "port": 8443,
            "users": [
              {
                "id": "f121ffc8-f6dc-4728-a871-a05e3f9cf8c5",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "usr-6b09ce88-api-v3.alcors.net",
          "fingerprint": "firefox"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-61",
      "protocol": "hysteria",
      "settings": {
        "version": 2,
        "address": "88.119.176.54",
        "port": 443
      },
      "streamSettings": {
        "network": "hysteria",
        "security": "tls",
        "method": "hysteria",
        "tlsSettings": {
          "serverName": "tuv10.harcho.shop"
        },
        "hysteriaSettings": {
          "version": 2,
          "auth": "f88bc31a-c30a-4a7f-bca6-5bc95d5bb593"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-62",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "45.194.66.30",
            "port": 443,
            "users": [
              {
                "id": "5a9af404-4b34-4f21-a6b3-5cf506579722",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "go-obsh-auto-drun.keno.su",
          "fingerprint": "firefox",
          "publicKey": "-r5xcA3iTzAf63kkb0VIILrLHH1VUq550pFZ-M74Jlc",
          "shortId": "de"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-63",
      "protocol": "hysteria",
      "settings": {
        "version": 2,
        "address": "89.37.192.54",
        "port": 443
      },
      "streamSettings": {
        "network": "hysteria",
        "security": "tls",
        "method": "hysteria",
        "tlsSettings": {
          "serverName": "ro-87-58-205-146.sslip.io"
        },
        "hysteriaSettings": {
          "version": 2,
          "auth": "6345ee32-7b62-4584-902d-07cfe588a02e"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-64",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "5.157.10.2",
            "port": 443,
            "users": [
              {
                "id": "f88bc31a-c30a-4a7f-bca6-5bc95d5bb593",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "reality",
        "realitySettings": {
          "serverName": "sweringa.rottshieldsons.pics",
          "fingerprint": "firefox",
          "publicKey": "x6p656szvu_3CKLsJ4NtkooRvdTVGx7IoPca_p58_jA",
          "shortId": "fb442438e2223836"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "tag": "proxy-65",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "153.56.231.73",
            "port": 443,
            "users": [
              {
                "id": "cda0862a-0f87-4be9-8ed8-1d0c9e382839",
                "encryption": "none",
                "level": 8
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "security": "reality",
        "realitySettings": {
          "serverName": "fc82dfx.nl8.h1clayd.click",
          "fingerprint": "ios",
          "publicKey": "dtO7khFLUkpFDQOtNzo4Th4hJKLoPSY2VtD_9k4Hgiw",
          "shortId": "7b2b1a14a6e0630d",
          "spiderX": "\/"
        },
        "xhttpSettings": {
          "path": "\/0616f2d729aa",
          "mode": "auto",
          "host": "fc82dfx.nl8.h1clayd.click"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "protocol": "freedom",
      "settings": {},
      "streamSettings": {
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      },
      "tag": "direct"
    },
    {
      "protocol": "blackhole",
      "tag": "block"
    }
  ],
  "policy": {
    "levels": {
      "0": {
        "connIdle": 300,
        "downlinkOnly": 1,
        "handshake": 4,
        "statsUserDownlink": true,
        "statsUserUplink": true,
        "uplinkOnly": 1
      },
      "8": {
        "connIdle": 300,
        "downlinkOnly": 1,
        "handshake": 4,
        "statsUserDownlink": true,
        "statsUserUplink": true,
        "uplinkOnly": 1
      }
    },
    "system": {
      "statsInboundDownlink": true,
      "statsInboundUplink": true,
      "statsOutboundDownlink": true,
      "statsOutboundUplink": true
    }
  },
  "remarks": "🇪🇺 Автовыбор",
  "routing": {
    "balancers": [
      {
        "selector": [
          "proxy"
        ],
        "strategy": {
          "type": "leastPing"
        },
        "tag": "balancer"
      }
    ],
    "domainStrategy": "AsIs",
    "rules": [
      {
        "inboundTag": [
          "metrics_in"
        ],
        "outboundTag": "metrics_out"
      },
      {
        "inboundTag": [
          "api_in"
        ],
        "outboundTag": "api"
      },
      {
        "ip": [
          "0.0.0.0\/32",
          "::\/128"
        ],
        "outboundTag": "block"
      },
      {
        "outboundTag": "block",
        "protocol": [
          "bittorrent"
        ]
      },
      {
        "outboundTag": "block",
        "port": "6881-6889,51413,21413,17417,37305"
      },
      {
        "domain": [
          "domain:oneme.ru",
          "domain:ip.mail.ru",
          "domain:2ip.ru",
          "domain:2ip.io",
          "domain:ipinfo.io",
          "domain:ip-api.com",
          "domain:ipwho.is",
          "domain:api.ipify.org",
          "domain:icanhazip.com",
          "domain:checkip.amazonaws.com",
          "domain:ifconfig.me",
          "domain:ident.me",
          "domain:ipleak.net",
          "domain:dnsleaktest.com",
          "domain:browserleaks.com"
        ],
        "outboundTag": "block"
      },
      {
        "ip": [
          "0.0.0.0\/8",
          "10.0.0.0\/8",
          "100.64.0.0\/10",
          "127.0.0.0\/8",
          "169.254.0.0\/16",
          "172.16.0.0\/12",
          "192.0.0.0\/24",
          "192.0.2.0\/24",
          "192.88.99.0\/24",
          "192.168.0.0\/16",
          "198.18.0.0\/15",
          "198.51.100.0\/24",
          "203.0.113.0\/24",
          "224.0.0.0\/3",
          "::\/127",
          "fc00::\/7",
          "fe80::\/10",
          "ff00::\/8",
          "224.0.0.0\/4",
          "255.255.255.255"
        ],
        "outboundTag": "direct"
      },
      {
        "balancerTag": "balancer",
        "ip": [
          "1.1.1.2",
          "1.0.0.2",
          "2606:4700:4700::1112",
          "2606:4700:4700::1002"
        ],
        "port": 443
      },
      {
        "balancerTag": "balancer",
        "domain": [
          "domain:security.cloudflare-dns.com"
        ],
        "port": 443
      },
      {
        "ip": [
          "77.88.8.88",
          "77.88.8.2",
          "2a02:6b8::feed:bad",
          "2a02:6b8:0:1::feed:bad"
        ],
        "outboundTag": "direct",
        "port": 443
      },
      {
        "domain": [
          "domain:safe.dot.dns.yandex.net"
        ],
        "outboundTag": "direct",
        "port": 443
      },
      {
        "outboundTag": "block",
        "protocol": [
          "quic"
        ]
      },
      {
        "balancerTag": "balancer",
        "ip": [
          "149.154.164.0\/22",
          "149.154.160.0\/20",
          "91.108.8.0\/22",
          "91.108.56.0\/22",
          "91.108.4.0\/22",
          "95.161.64.0\/20",
          "149.154.167.0\/24",
          "91.108.16.0\/22",
          "91.108.12.0\/22",
          "91.105.192.0\/23",
          "91.108.20.0\/22",
          "185.76.151.0\/24",
          "149.154.167.0\/20",
          "5.28.128.0\/17"
        ]
      },
      {
        "domain": [
          "domain:push.apple.com",
          "domain:api.push.apple.com",
          "domain:courier.push.apple.com",
          "domain:gateway.push.apple.com",
          "domain:feedback.push.apple.com",
          "domain:mtalk.google.com",
          "domain:fcm.googleapis.com",
          "domain:firebaseinstallations.googleapis.com",
          "domain:firebase.googleapis.com",
          "domain:firebaseappcheck.googleapis.com",
          "domain:android.clients.google.com",
          "domain:push-api.cloud.huawei.com",
          "domain:hms-push-api.cloud.huawei.com",
          "domain:push.xiaomi.com",
          "domain:api.xiaomi.com",
          "domain:push.samsungosp.com",
          "domain:updates.push.services.mozilla.com"
        ],
        "outboundTag": "direct"
      },
      {
        "domain": [
          "domain:roblox.com",
          "domain:rbxcdn.com",
          "domain:rbx.com",
          "domain:roblox.cn",
          "domain:robloxusercontent.com",
          "domain:robloxapi.com"
        ],
        "balancerTag": "balancer"
      },
      {
        "balancerTag": "balancer",
        "domain": [
          "domain:t.me",
          "domain:tg.dev",
          "domain:tg.org",
          "domain:tx.me",
          "domain:teleg.xyz",
          "domain:tgcloud.ai",
          "domain:telegram.ai",
          "domain:telegram.asia",
          "domain:telegram.biz",
          "domain:telegram.cloud",
          "domain:telegram.cn",
          "domain:telegram.co",
          "domain:telegram.com",
          "domain:telegram.de",
          "domain:telegram.dev",
          "domain:telegram.dog",
          "domain:telegram.eu",
          "domain:telegram.fr",
          "domain:telegram.host",
          "domain:telegram.in",
          "domain:telegram.info",
          "domain:telegram.io",
          "domain:telegram.jp",
          "domain:telegram.me",
          "domain:telegram.net",
          "domain:telegram.org",
          "domain:telegram.qa",
          "domain:telegram.ru",
          "domain:telegram.services",
          "domain:telegram.solutions",
          "domain:telegram.space",
          "domain:telegram.team",
          "domain:telegram.tech",
          "domain:telegram.uk",
          "domain:telegram.us",
          "domain:telegram.website",
          "domain:telegram.xyz",
          "domain:telegramapp.org",
          "domain:telegra.ph",
          "domain:telesco.pe",
          "domain:nicegram.app",
          "domain:telegramdownload.com",
          "domain:cdn-telegram.org",
          "domain:comments.app",
          "domain:contest.com",
          "domain:fragment.com",
          "domain:graph.org",
          "domain:quiz.directory",
          "domain:tdesktop.com",
          "domain:telega.one",
          "domain:telegram-cdn.org",
          "domain:usercontent.dev",
          "domain:tgram.org",
          "domain:torg.org"
        ]
      },
      {
        "domain": [
          "domain:ru",
          "domain:su",
          "domain:xn--p1ai",
          "domain:yandex.ru",
          "domain:yandex.net",
          "domain:yastatic.net",
          "domain:yandex.com",
          "domain:vk.com",
          "domain:vk.ru",
          "domain:vk.me",
          "domain:userapi.com",
          "domain:vkuseraudio.net",
          "domain:vk-cdn.net",
          "domain:vk-portal.net",
          "domain:ok.ru",
          "domain:mail.ru",
          "domain:my.mail.ru",
          "domain:avito.ru",
          "domain:ozon.ru",
          "domain:wildberries.ru",
          "domain:sberbank.ru",
          "domain:online.sberbank.ru",
          "domain:alfabank.ru",
          "domain:alfa-bank.ru",
          "domain:tbank.ru",
          "domain:tinkoff.ru",
          "domain:vtb.ru",
          "domain:gazprombank.ru",
          "domain:gosuslugi.ru",
          "domain:nalog.ru",
          "domain:mos.ru",
          "domain:mosreg.ru",
          "domain:rzd.ru",
          "domain:pochta.ru",
          "domain:aeroflot.ru",
          "domain:2gis.ru",
          "domain:hh.ru",
          "domain:kinopoisk.ru",
          "domain:ivi.ru",
          "domain:rutube.ru",
          "domain:vkvideo.ru",
          "domain:ya.ru",
          "domain:yandex.by",
          "domain:yandex.kz",
          "domain:yandexcloud.net",
          "domain:yandexcloud.ru",
          "domain:yandex-team.ru",
          "domain:yandex-team.com",
          "domain:yastat.net",
          "domain:yandexmaps.com",
          "domain:yandexmaps.net",
          "domain:yandex.st",
          "domain:dzen.ru",
          "domain:edadeal.ru",
          "domain:toloka.ai",
          "domain:vk.cc",
          "domain:vk.link",
          "domain:vk.team",
          "domain:vk.company",
          "domain:vkuservideo.net",
          "domain:vkuserlive.net",
          "domain:odnoklassniki.ru",
          "domain:odkl.ru",
          "domain:list.ru",
          "domain:inbox.ru",
          "domain:bk.ru",
          "domain:cloud.mail.ru",
          "domain:sber.ru",
          "domain:sberdevices.ru",
          "domain:sberbank.com",
          "domain:sbermarket.ru",
          "domain:alfabank.com",
          "domain:tinkoffjournal.ru",
          "domain:vtb.com",
          "domain:gpb.ru",
          "domain:rshb.ru",
          "domain:psbank.ru",
          "domain:sovcombank.ru",
          "domain:domrf.ru",
          "domain:cbr.ru",
          "domain:banki.ru",
          "domain:yoomoney.ru",
          "domain:yoomoney.com",
          "domain:nspk.ru",
          "domain:mironline.ru",
          "domain:koronapay.com",
          "domain:nalog.gov.ru",
          "domain:sfr.gov.ru",
          "domain:pfr.gov.ru",
          "domain:fssp.gov.ru",
          "domain:rosreestr.gov.ru",
          "domain:pravo.gov.ru",
          "domain:publication.pravo.gov.ru",
          "domain:government.ru",
          "domain:kremlin.ru",
          "domain:minfin.gov.ru",
          "domain:customs.gov.ru",
          "domain:zakupki.gov.ru",
          "domain:bus.gov.ru",
          "domain:sudrf.ru",
          "domain:kad.arbitr.ru",
          "domain:gov.spb.ru",
          "domain:spb.ru",
          "domain:tatarstan.ru",
          "domain:kzn.ru",
          "domain:youla.ru",
          "domain:lamoda.ru",
          "domain:detmir.ru",
          "domain:dns-shop.ru",
          "domain:citilink.ru",
          "domain:mvideo.ru",
          "domain:eldorado.ru",
          "domain:hoff.ru",
          "domain:lemanapro.ru",
          "domain:drom.ru",
          "domain:auto.ru",
          "domain:drive2.ru",
          "domain:vkusvill.ru",
          "domain:magnit.ru",
          "domain:magnitmarket.ru",
          "domain:lenta.com",
          "domain:perekrestok.ru",
          "domain:5ka.ru",
          "domain:kuper.ru",
          "domain:samokat.ru",
          "domain:delivery-club.ru",
          "domain:chizhik.ru",
          "domain:metro-cc.ru",
          "domain:okko.tv",
          "domain:wink.ru",
          "domain:kion.ru",
          "domain:start.ru",
          "domain:premier.one",
          "domain:more.tv",
          "domain:smotrim.ru",
          "domain:ntv.ru",
          "domain:1tv.ru",
          "domain:matchtv.ru",
          "domain:sportbox.ru",
          "domain:championat.com",
          "domain:sports.ru",
          "domain:rbc.ru",
          "domain:ria.ru",
          "domain:tass.ru",
          "domain:interfax.ru",
          "domain:lenta.ru",
          "domain:fontanka.ru",
          "domain:kp.ru",
          "domain:rg.ru",
          "domain:aif.ru",
          "domain:gazeta.ru",
          "domain:vedomosti.ru",
          "domain:kommersant.ru",
          "domain:iz.ru",
          "domain:mk.ru",
          "domain:rzd-bonus.ru",
          "domain:russianpost.ru",
          "domain:post.ru",
          "domain:pobeda.aero",
          "domain:s7.ru",
          "domain:utair.ru",
          "domain:smartavia.com",
          "domain:azimuth.aero",
          "domain:tutu.ru",
          "domain:aviasales.ru",
          "domain:2gis.com",
          "domain:rabota.ru",
          "domain:superjob.ru",
          "domain:kontur.ru",
          "domain:sbis.ru",
          "domain:diadoc.ru",
          "domain:kontur-extern.ru",
          "domain:rostelecom.ru",
          "domain:rt.ru",
          "domain:mts.ru",
          "domain:beeline.ru",
          "domain:megafon.ru",
          "domain:t2.ru",
          "domain:tele2.ru",
          "domain:yota.ru",
          "domain:dom.ru",
          "domain:ertelecom.ru",
          "domain:ngenix.net",
          "domain:cdnmail.ru",
          "domain:cdnvideo.ru",
          "domain:rambler.ru"
        ],
        "outboundTag": "direct"
      },
      {
        "balancerTag": "balancer",
        "network": "tcp,udp"
      }
    ]
  },
  "stats": {}
}

{"api":{"services":["StatsService"],"tag":"api"},"burstObservatory":{"pingConfig":{"connectivity":"https:\/\/browser.yandex.ru\/generate_204","destination":"https:\/\/www.google.com","httpMethod":"GET","interval":"15s","sampling":4,"timeout":"2s"},"subjectSelector":["proxy"]},"dns":{"disableCache":false,"hosts":{"lkfl2.nalog.ru":["213.24.64.175","213.24.64.17"],"lknpd.nalog.ru":["213.24.64.181"],"safe.dot.dns.yandex.net":["77.88.8.88","77.88.8.2","2a02:6b8::feed:bad","2a02:6b8:0:1::feed:bad"],"security.cloudflare-dns.com":["1.1.1.2","1.0.0.2","2606:4700:4700::1112","2606:4700:4700::1002"]},"queryStrategy":"UseIPv4","serveExpiredTTL":10,"serveStale":true,"servers":["https:\/\/security.cloudflare-dns.com\/dns-query","https+local:\/\/security.cloudflare-dns.com\/dns-query","https+local:\/\/dns.google\/dns-query","tcp+local:\/\/77.88.8.88:53"],"useSystemHosts":true},"inbounds":[{"listen":"127.0.0.1","port":10808,"protocol":"socks","settings":{"auth":"noauth","udp":true,"userLevel":8},"sniffing":{"destOverride":["http","tls","quic"],"enabled":true,"routeOnly":true},"tag":"socks"},{"listen":"127.0.0.1","port":10809,"protocol":"http","settings":{"userLevel":8},"sniffing":{"destOverride":["http","tls","quic"],"enabled":true,"routeOnly":true},"tag":"http"},{"listen":"127.0.0.1","port":11111,"protocol":"dokodemo-door","settings":{"address":"127.0.0.1"},"tag":"metrics_in"},{"listen":"127.0.0.1","port":10085,"protocol":"dokodemo-door","settings":{"address":"127.0.0.1"},"tag":"api_in"}],"log":{"loglevel":"warning"},"meta":null,"metrics":{"tag":"metrics_out"},"outbounds":[{"tag":"proxy-1","protocol":"vless","settings":{"vnext":[{"address":"45.33.75.68","port":443,"users":[{"id":"e3c6ed3a-b758-443c-aef1-112fa24019c3","encryption":"none","level":8,"flow":"xtls-rprx-vision"}]}]},"streamSettings":{"network":"tcp","security":"reality","realitySettings":{"serverName":"amp-api-edge.apps.apple.com","fingerprint":"firefox","publicKey":"P-lHtRBeKWqfMfOoOF5dvfwEvU0geEkMuUXqFtF7yjQ","shortId":"75beb3e297f4f26d"},"sockopt":{"domainStrategy":"UseIPv4","tcpKeepAliveIdle":60,"tcpKeepAliveInterval":15,"tcpNoDelay":true}}},{"tag":"proxy-2","protocol":"vless","settings":{"vnext":[{"address":"152.232.82.196","port":443,"users":[{"id":"2a7bf1d0-c4ef-43a6-b62a-22821db65b5e","encryption":"none","level":8,"flow":"xtls-rprx-vision"}]}]},"streamSettings":{"network":"tcp","security":"reality","realitySettings":{"serverName":"api.videobereg.cc","fingerprint":"firefox","publicKey":"r5WB5FnSCt4eeBC1FJMfkWHbzsMuabo0Rc6wuAhlZUs","shortId":"a8"},"sockopt":{"domainStrategy":"UseIPv4","tcpKeepAliveIdle":60,"tcpKeepAliveInterval":15,"tcpNoDelay":true}}},{"tag":"proxy-3","protocol":"vless","settings":{"vnext":[{"address":"170.114.45.6","port":443,"users":[{"id":"bc0f9e3a-6dad-42d5-b09f-dff4cdf57437","encryption":"none","level":8}]}]},"streamSettings":{"network":"ws","security":"tls","tlsSettings":{"serverName":"googleapis.hmacreation.eu.cc","fingerprint":"firefox"},"wsSettings":{"path":"\/","headers":{"Host":"googleapis.hmacreation.eu.cc"}},"sockopt":{"domainStrategy":"UseIPv4","tcpKeepAliveIdle":60,"tcpKeepAliveInterval":15,"tcpNoDelay":true}}},{"tag":"proxy-4","protocol":"vless","settings":{"vnext":[{"address":"45.88.162.111","port":8443,"users":[{"id":"749b1c56-e658-4bf5-94bd-5c3286a4aed1","encryption":"none","level":8}]}]},"streamSettings":{"network":"xhttp","security":"tls","tlsSettings":{"serverName":"turntable.elvano.website","fingerprint":"firefox","alpn":["h2"]},"xhttpSettings":{"path":"\/api\/preview\/","mode":"packet-up","host":"turntable.elvano.website"},"sockopt":{"domainStrategy":"UseIPv4","tcpKeepAliveIdle":60,"tcpKeepAliveInterval":15,"tcpNoDelay":true}}},{"protocol":"freedom","settings":{},"streamSettings":{"sockopt":{"domainStrategy":"UseIPv4","tcpKeepAliveIdle":60,"tcpKeepAliveInterval":15,"tcpNoDelay":true}},"tag":"direct"},{"protocol":"blackhole","tag":"block"}],"policy":{"levels":{"0":{"connIdle":300,"downlinkOnly":1,"handshake":4,"statsUserDownlink":true,"statsUserUplink":true,"uplinkOnly":1},"8":{"connIdle":300,"downlinkOnly":1,"handshake":4,"statsUserDownlink":true,"statsUserUplink":true,"uplinkOnly":1}},"system":{"statsInboundDownlink":true,"statsInboundUplink":true,"statsOutboundDownlink":true,"statsOutboundUplink":true}},"remarks":"🇺🇸 США","routing":{"balancers":[{"selector":["proxy"],"strategy":{"type":"leastPing"},"tag":"balancer"}],"domainStrategy":"AsIs","rules":[{"inboundTag":["metrics_in"],"outboundTag":"metrics_out"},{"inboundTag":["api_in"],"outboundTag":"api"},{"ip":["0.0.0.0\/32","::\/128"],"outboundTag":"block"},{"outboundTag":"block","protocol":["bittorrent"]},{"outboundTag":"block","port":"6881-6889,51413,21413,17417,37305"},{"domain":["domain:oneme.ru","domain:ip.mail.ru","domain:2ip.ru","domain:2ip.io","domain:ipinfo.io","domain:ip-api.com","domain:ipwho.is","domain:api.ipify.org","domain:icanhazip.com","domain:checkip.amazonaws.com","domain:ifconfig.me","domain:ident.me","domain:ipleak.net","domain:dnsleaktest.com","domain:browserleaks.com"],"outboundTag":"block"},{"ip":["0.0.0.0\/8","10.0.0.0\/8","100.64.0.0\/10","127.0.0.0\/8","169.254.0.0\/16","172.16.0.0\/12","192.0.0.0\/24","192.0.2.0\/24","192.88.99.0\/24","192.168.0.0\/16","198.18.0.0\/15","198.51.100.0\/24","203.0.113.0\/24","224.0.0.0\/3","::\/127","fc00::\/7","fe80::\/10","ff00::\/8","224.0.0.0\/4","255.255.255.255"],"outboundTag":"direct"},{"balancerTag":"balancer","ip":["1.1.1.2","1.0.0.2","2606:4700:4700::1112","2606:4700:4700::1002"],"port":443},{"balancerTag":"balancer","domain":["domain:security.cloudflare-dns.com"],"port":443},{"ip":["77.88.8.88","77.88.8.2","2a02:6b8::feed:bad","2a02:6b8:0:1::feed:bad"],"outboundTag":"direct","port":443},{"domain":["domain:safe.dot.dns.yandex.net"],"outboundTag":"direct","port":443},{"outboundTag":"block","protocol":["quic"]},{"balancerTag":"balancer","ip":["149.154.164.0\/22","149.154.160.0\/20","91.108.8.0\/22","91.108.56.0\/22","91.108.4.0\/22","95.161.64.0\/20","149.154.167.0\/24","91.108.16.0\/22","91.108.12.0\/22","91.105.192.0\/23","91.108.20.0\/22","185.76.151.0\/24","149.154.167.0\/20","5.28.128.0\/17"]},{"domain":["domain:push.apple.com","domain:api.push.apple.com","domain:courier.push.apple.com","domain:gateway.push.apple.com","domain:feedback.push.apple.com","domain:mtalk.google.com","domain:fcm.googleapis.com","domain:firebaseinstallations.googleapis.com","domain:firebase.googleapis.com","domain:firebaseappcheck.googleapis.com","domain:android.clients.google.com","domain:push-api.cloud.huawei.com","domain:hms-push-api.cloud.huawei.com","domain:push.xiaomi.com","domain:api.xiaomi.com","domain:push.samsungosp.com","domain:updates.push.services.mozilla.com"],"outboundTag":"direct"},{"domain":["domain:roblox.com","domain:rbxcdn.com","domain:rbx.com","domain:roblox.cn","domain:robloxusercontent.com","domain:robloxapi.com"],"balancerTag":"balancer"},{"balancerTag":"balancer","domain":["domain:t.me","domain:tg.dev","domain:tg.org","domain:tx.me","domain:teleg.xyz","domain:tgcloud.ai","domain:telegram.ai","domain:telegram.asia","domain:telegram.biz","domain:telegram.cloud","domain:telegram.cn","domain:telegram.co","domain:telegram.com","domain:telegram.de","domain:telegram.dev","domain:telegram.dog","domain:telegram.eu","domain:telegram.fr","domain:telegram.host","domain:telegram.in","domain:telegram.info","domain:telegram.io","domain:telegram.jp","domain:telegram.me","domain:telegram.net","domain:telegram.org","domain:telegram.qa","domain:telegram.ru","domain:telegram.services","domain:telegram.solutions","domain:telegram.space","domain:telegram.team","domain:telegram.tech","domain:telegram.uk","domain:telegram.us","domain:telegram.website","domain:telegram.xyz","domain:telegramapp.org","domain:telegra.ph","domain:telesco.pe","domain:nicegram.app","domain:telegramdownload.com","domain:cdn-telegram.org","domain:comments.app","domain:contest.com","domain:fragment.com","domain:graph.org","domain:quiz.directory","domain:tdesktop.com","domain:telega.one","domain:telegram-cdn.org","domain:usercontent.dev","domain:tgram.org","domain:torg.org"]},{"domain":["domain:ru","domain:su","domain:xn--p1ai","domain:yandex.ru","domain:yandex.net","domain:yastatic.net","domain:yandex.com","domain:vk.com","domain:vk.ru","domain:vk.me","domain:userapi.com","domain:vkuseraudio.net","domain:vk-cdn.net","domain:vk-portal.net","domain:ok.ru","domain:mail.ru","domain:my.mail.ru","domain:avito.ru","domain:ozon.ru","domain:wildberries.ru","domain:sberbank.ru","domain:online.sberbank.ru","domain:alfabank.ru","domain:alfa-bank.ru","domain:tbank.ru","domain:tinkoff.ru","domain:vtb.ru","domain:gazprombank.ru","domain:gosuslugi.ru","domain:nalog.ru","domain:mos.ru","domain:mosreg.ru","domain:rzd.ru","domain:pochta.ru","domain:aeroflot.ru","domain:2gis.ru","domain:hh.ru","domain:kinopoisk.ru","domain:ivi.ru","domain:rutube.ru","domain:vkvideo.ru","domain:ya.ru","domain:yandex.by","domain:yandex.kz","domain:yandexcloud.net","domain:yandexcloud.ru","domain:yandex-team.ru","domain:yandex-team.com","domain:yastat.net","domain:yandexmaps.com","domain:yandexmaps.net","domain:yandex.st","domain:dzen.ru","domain:edadeal.ru","domain:toloka.ai","domain:vk.cc","domain:vk.link","domain:vk.team","domain:vk.company","domain:vkuservideo.net","domain:vkuserlive.net","domain:odnoklassniki.ru","domain:odkl.ru","domain:list.ru","domain:inbox.ru","domain:bk.ru","domain:cloud.mail.ru","domain:sber.ru","domain:sberdevices.ru","domain:sberbank.com","domain:sbermarket.ru","domain:alfabank.com","domain:tinkoffjournal.ru","domain:vtb.com","domain:gpb.ru","domain:rshb.ru","domain:psbank.ru","domain:sovcombank.ru","domain:domrf.ru","domain:cbr.ru","domain:banki.ru","domain:yoomoney.ru","domain:yoomoney.com","domain:nspk.ru","domain:mironline.ru","domain:koronapay.com","domain:nalog.gov.ru","domain:sfr.gov.ru","domain:pfr.gov.ru","domain:fssp.gov.ru","domain:rosreestr.gov.ru","domain:pravo.gov.ru","domain:publication.pravo.gov.ru","domain:government.ru","domain:kremlin.ru","domain:minfin.gov.ru","domain:customs.gov.ru","domain:zakupki.gov.ru","domain:bus.gov.ru","domain:sudrf.ru","domain:kad.arbitr.ru","domain:gov.spb.ru","domain:spb.ru","domain:tatarstan.ru","domain:kzn.ru","domain:youla.ru","domain:lamoda.ru","domain:detmir.ru","domain:dns-shop.ru","domain:citilink.ru","domain:mvideo.ru","domain:eldorado.ru","domain:hoff.ru","domain:lemanapro.ru","domain:drom.ru","domain:auto.ru","domain:drive2.ru","domain:vkusvill.ru","domain:magnit.ru","domain:magnitmarket.ru","domain:lenta.com","domain:perekrestok.ru","domain:5ka.ru","domain:kuper.ru","domain:samokat.ru","domain:delivery-club.ru","domain:chizhik.ru","domain:metro-cc.ru","domain:okko.tv","domain:wink.ru","domain:kion.ru","domain:start.ru","domain:premier.one","domain:more.tv","domain:smotrim.ru","domain:ntv.ru","domain:1tv.ru","domain:matchtv.ru","domain:sportbox.ru","domain:championat.com","domain:sports.ru","domain:rbc.ru","domain:ria.ru","domain:tass.ru","domain:interfax.ru","domain:lenta.ru","domain:fontanka.ru","domain:kp.ru","domain:rg.ru","domain:aif.ru","domain:gazeta.ru","domain:vedomosti.ru","domain:kommersant.ru","domain:iz.ru","domain:mk.ru","domain:rzd-bonus.ru","domain:russianpost.ru","domain:post.ru","domain:pobeda.aero","domain:s7.ru","domain:utair.ru","domain:smartavia.com","domain:azimuth.aero","domain:tutu.ru","domain:aviasales.ru","domain:2gis.com","domain:rabota.ru","domain:superjob.ru","domain:kontur.ru","domain:sbis.ru","domain:diadoc.ru","domain:kontur-extern.ru","domain:rostelecom.ru","domain:rt.ru","domain:mts.ru","domain:beeline.ru","domain:megafon.ru","domain:t2.ru","domain:tele2.ru","domain:yota.ru","domain:dom.ru","domain:ertelecom.ru","domain:ngenix.net","domain:cdnmail.ru","domain:cdnvideo.ru","domain:rambler.ru"],"outboundTag":"direct"},{"balancerTag":"balancer","network":"tcp,udp"}]},"stats":{}}


{
  "api": {
    "services": [
      "StatsService"
    ],
    "tag": "api"
  },
  "burstObservatory": {
    "pingConfig": {
      "connectivity": "https:\/\/browser.yandex.ru\/generate_204",
      "destination": "https:\/\/www.google.com",
      "httpMethod": "GET",
      "interval": "15s",
      "sampling": 4,
      "timeout": "2s"
    },
    "subjectSelector": [
      "proxy"
    ]
  },
  "dns": {
    "disableCache": false,
    "hosts": {
      "lkfl2.nalog.ru": [
        "213.24.64.175",
        "213.24.64.17"
      ],
      "lknpd.nalog.ru": [
        "213.24.64.181"
      ],
      "safe.dot.dns.yandex.net": [
        "77.88.8.88",
        "77.88.8.2",
        "2a02:6b8::feed:bad",
        "2a02:6b8:0:1::feed:bad"
      ],
      "security.cloudflare-dns.com": [
        "1.1.1.2",
        "1.0.0.2",
        "2606:4700:4700::1112",
        "2606:4700:4700::1002"
      ]
    },
    "queryStrategy": "UseIPv4",
    "serveExpiredTTL": 10,
    "serveStale": true,
    "servers": [
      "https:\/\/security.cloudflare-dns.com\/dns-query",
      "https+local:\/\/security.cloudflare-dns.com\/dns-query",
      "https+local:\/\/dns.google\/dns-query",
      "tcp+local:\/\/77.88.8.88:53"
    ],
    "useSystemHosts": true
  },
  "inbounds": [
    {
      "listen": "127.0.0.1",
      "port": 10808,
      "protocol": "socks",
      "settings": {
        "auth": "noauth",
        "udp": true,
        "userLevel": 8
      },
      "sniffing": {
        "destOverride": [
          "http",
          "tls",
          "quic"
        ],
        "enabled": true,
        "routeOnly": true
      },
      "tag": "socks"
    },
    {
      "listen": "127.0.0.1",
      "port": 10809,
      "protocol": "http",
      "settings": {
        "userLevel": 8
      },
      "sniffing": {
        "destOverride": [
          "http",
          "tls",
          "quic"
        ],
        "enabled": true,
        "routeOnly": true
      },
      "tag": "http"
    },
    {
      "listen": "127.0.0.1",
      "port": 11111,
      "protocol": "dokodemo-door",
      "settings": {
        "address": "127.0.0.1"
      },
      "tag": "metrics_in"
    },
    {
      "listen": "127.0.0.1",
      "port": 10085,
      "protocol": "dokodemo-door",
      "settings": {
        "address": "127.0.0.1"
      },
      "tag": "api_in"
    }
  ],
  "log": {
    "loglevel": "warning"
  },
  "meta": null,
  "metrics": {
    "tag": "metrics_out"
  },
  "outbounds": [
    {
      "tag": "proxy-1",
      "protocol": "hysteria",
      "settings": {
        "version": 2,
        "address": "88.119.176.54",
        "port": 443
      },
      "streamSettings": {
        "network": "hysteria",
        "security": "tls",
        "method": "hysteria",
        "tlsSettings": {
          "serverName": "tuv10.harcho.shop"
        },
        "hysteriaSettings": {
          "version": 2,
          "auth": "f88bc31a-c30a-4a7f-bca6-5bc95d5bb593"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "protocol": "freedom",
      "settings": {},
      "streamSettings": {
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      },
      "tag": "direct"
    },
    {
      "protocol": "blackhole",
      "tag": "block"
    }
  ],
  "policy": {
    "levels": {
      "0": {
        "connIdle": 300,
        "downlinkOnly": 1,
        "handshake": 4,
        "statsUserDownlink": true,
        "statsUserUplink": true,
        "uplinkOnly": 1
      },
      "8": {
        "connIdle": 300,
        "downlinkOnly": 1,
        "handshake": 4,
        "statsUserDownlink": true,
        "statsUserUplink": true,
        "uplinkOnly": 1
      }
    },
    "system": {
      "statsInboundDownlink": true,
      "statsInboundUplink": true,
      "statsOutboundDownlink": true,
      "statsOutboundUplink": true
    }
  },
  "remarks": "🇱🇹 Литва",
  "routing": {
    "balancers": [
      {
        "selector": [
          "proxy"
        ],
        "strategy": {
          "type": "leastPing"
        },
        "tag": "balancer"
      }
    ],
    "domainStrategy": "AsIs",
    "rules": [
      {
        "inboundTag": [
          "metrics_in"
        ],
        "outboundTag": "metrics_out"
      },
      {
        "inboundTag": [
          "api_in"
        ],
        "outboundTag": "api"
      },
      {
        "ip": [
          "0.0.0.0\/32",
          "::\/128"
        ],
        "outboundTag": "block"
      },
      {
        "outboundTag": "block",
        "protocol": [
          "bittorrent"
        ]
      },
      {
        "outboundTag": "block",
        "port": "6881-6889,51413,21413,17417,37305"
      },
      {
        "domain": [
          "domain:oneme.ru",
          "domain:ip.mail.ru",
          "domain:2ip.ru",
          "domain:2ip.io",
          "domain:ipinfo.io",
          "domain:ip-api.com",
          "domain:ipwho.is",
          "domain:api.ipify.org",
          "domain:icanhazip.com",
          "domain:checkip.amazonaws.com",
          "domain:ifconfig.me",
          "domain:ident.me",
          "domain:ipleak.net",
          "domain:dnsleaktest.com",
          "domain:browserleaks.com"
        ],
        "outboundTag": "block"
      },
      {
        "ip": [
          "0.0.0.0\/8",
          "10.0.0.0\/8",
          "100.64.0.0\/10",
          "127.0.0.0\/8",
          "169.254.0.0\/16",
          "172.16.0.0\/12",
          "192.0.0.0\/24",
          "192.0.2.0\/24",
          "192.88.99.0\/24",
          "192.168.0.0\/16",
          "198.18.0.0\/15",
          "198.51.100.0\/24",
          "203.0.113.0\/24",
          "224.0.0.0\/3",
          "::\/127",
          "fc00::\/7",
          "fe80::\/10",
          "ff00::\/8",
          "224.0.0.0\/4",
          "255.255.255.255"
        ],
        "outboundTag": "direct"
      },
      {
        "balancerTag": "balancer",
        "ip": [
          "1.1.1.2",
          "1.0.0.2",
          "2606:4700:4700::1112",
          "2606:4700:4700::1002"
        ],
        "port": 443
      },
      {
        "balancerTag": "balancer",
        "domain": [
          "domain:security.cloudflare-dns.com"
        ],
        "port": 443
      },
      {
        "ip": [
          "77.88.8.88",
          "77.88.8.2",
          "2a02:6b8::feed:bad",
          "2a02:6b8:0:1::feed:bad"
        ],
        "outboundTag": "direct",
        "port": 443
      },
      {
        "domain": [
          "domain:safe.dot.dns.yandex.net"
        ],
        "outboundTag": "direct",
        "port": 443
      },
      {
        "outboundTag": "block",
        "protocol": [
          "quic"
        ]
      },
      {
        "balancerTag": "balancer",
        "ip": [
          "149.154.164.0\/22",
          "149.154.160.0\/20",
          "91.108.8.0\/22",
          "91.108.56.0\/22",
          "91.108.4.0\/22",
          "95.161.64.0\/20",
          "149.154.167.0\/24",
          "91.108.16.0\/22",
          "91.108.12.0\/22",
          "91.105.192.0\/23",
          "91.108.20.0\/22",
          "185.76.151.0\/24",
          "149.154.167.0\/20",
          "5.28.128.0\/17"
        ]
      },
      {
        "domain": [
          "domain:push.apple.com",
          "domain:api.push.apple.com",
          "domain:courier.push.apple.com",
          "domain:gateway.push.apple.com",
          "domain:feedback.push.apple.com",
          "domain:mtalk.google.com",
          "domain:fcm.googleapis.com",
          "domain:firebaseinstallations.googleapis.com",
          "domain:firebase.googleapis.com",
          "domain:firebaseappcheck.googleapis.com",
          "domain:android.clients.google.com",
          "domain:push-api.cloud.huawei.com",
          "domain:hms-push-api.cloud.huawei.com",
          "domain:push.xiaomi.com",
          "domain:api.xiaomi.com",
          "domain:push.samsungosp.com",
          "domain:updates.push.services.mozilla.com"
        ],
        "outboundTag": "direct"
      },
      {
        "domain": [
          "domain:roblox.com",
          "domain:rbxcdn.com",
          "domain:rbx.com",
          "domain:roblox.cn",
          "domain:robloxusercontent.com",
          "domain:robloxapi.com"
        ],
        "balancerTag": "balancer"
      },
      {
        "balancerTag": "balancer",
        "domain": [
          "domain:t.me",
          "domain:tg.dev",
          "domain:tg.org",
          "domain:tx.me",
          "domain:teleg.xyz",
          "domain:tgcloud.ai",
          "domain:telegram.ai",
          "domain:telegram.asia",
          "domain:telegram.biz",
          "domain:telegram.cloud",
          "domain:telegram.cn",
          "domain:telegram.co",
          "domain:telegram.com",
          "domain:telegram.de",
          "domain:telegram.dev",
          "domain:telegram.dog",
          "domain:telegram.eu",
          "domain:telegram.fr",
          "domain:telegram.host",
          "domain:telegram.in",
          "domain:telegram.info",
          "domain:telegram.io",
          "domain:telegram.jp",
          "domain:telegram.me",
          "domain:telegram.net",
          "domain:telegram.org",
          "domain:telegram.qa",
          "domain:telegram.ru",
          "domain:telegram.services",
          "domain:telegram.solutions",
          "domain:telegram.space",
          "domain:telegram.team",
          "domain:telegram.tech",
          "domain:telegram.uk",
          "domain:telegram.us",
          "domain:telegram.website",
          "domain:telegram.xyz",
          "domain:telegramapp.org",
          "domain:telegra.ph",
          "domain:telesco.pe",
          "domain:nicegram.app",
          "domain:telegramdownload.com",
          "domain:cdn-telegram.org",
          "domain:comments.app",
          "domain:contest.com",
          "domain:fragment.com",
          "domain:graph.org",
          "domain:quiz.directory",
          "domain:tdesktop.com",
          "domain:telega.one",
          "domain:telegram-cdn.org",
          "domain:usercontent.dev",
          "domain:tgram.org",
          "domain:torg.org"
        ]
      },
      {
        "domain": [
          "domain:ru",
          "domain:su",
          "domain:xn--p1ai",
          "domain:yandex.ru",
          "domain:yandex.net",
          "domain:yastatic.net",
          "domain:yandex.com",
          "domain:vk.com",
          "domain:vk.ru",
          "domain:vk.me",
          "domain:userapi.com",
          "domain:vkuseraudio.net",
          "domain:vk-cdn.net",
          "domain:vk-portal.net",
          "domain:ok.ru",
          "domain:mail.ru",
          "domain:my.mail.ru",
          "domain:avito.ru",
          "domain:ozon.ru",
          "domain:wildberries.ru",
          "domain:sberbank.ru",
          "domain:online.sberbank.ru",
          "domain:alfabank.ru",
          "domain:alfa-bank.ru",
          "domain:tbank.ru",
          "domain:tinkoff.ru",
          "domain:vtb.ru",
          "domain:gazprombank.ru",
          "domain:gosuslugi.ru",
          "domain:nalog.ru",
          "domain:mos.ru",
          "domain:mosreg.ru",
          "domain:rzd.ru",
          "domain:pochta.ru",
          "domain:aeroflot.ru",
          "domain:2gis.ru",
          "domain:hh.ru",
          "domain:kinopoisk.ru",
          "domain:ivi.ru",
          "domain:rutube.ru",
          "domain:vkvideo.ru",
          "domain:ya.ru",
          "domain:yandex.by",
          "domain:yandex.kz",
          "domain:yandexcloud.net",
          "domain:yandexcloud.ru",
          "domain:yandex-team.ru",
          "domain:yandex-team.com",
          "domain:yastat.net",
          "domain:yandexmaps.com",
          "domain:yandexmaps.net",
          "domain:yandex.st",
          "domain:dzen.ru",
          "domain:edadeal.ru",
          "domain:toloka.ai",
          "domain:vk.cc",
          "domain:vk.link",
          "domain:vk.team",
          "domain:vk.company",
          "domain:vkuservideo.net",
          "domain:vkuserlive.net",
          "domain:odnoklassniki.ru",
          "domain:odkl.ru",
          "domain:list.ru",
          "domain:inbox.ru",
          "domain:bk.ru",
          "domain:cloud.mail.ru",
          "domain:sber.ru",
          "domain:sberdevices.ru",
          "domain:sberbank.com",
          "domain:sbermarket.ru",
          "domain:alfabank.com",
          "domain:tinkoffjournal.ru",
          "domain:vtb.com",
          "domain:gpb.ru",
          "domain:rshb.ru",
          "domain:psbank.ru",
          "domain:sovcombank.ru",
          "domain:domrf.ru",
          "domain:cbr.ru",
          "domain:banki.ru",
          "domain:yoomoney.ru",
          "domain:yoomoney.com",
          "domain:nspk.ru",
          "domain:mironline.ru",
          "domain:koronapay.com",
          "domain:nalog.gov.ru",
          "domain:sfr.gov.ru",
          "domain:pfr.gov.ru",
          "domain:fssp.gov.ru",
          "domain:rosreestr.gov.ru",
          "domain:pravo.gov.ru",
          "domain:publication.pravo.gov.ru",
          "domain:government.ru",
          "domain:kremlin.ru",
          "domain:minfin.gov.ru",
          "domain:customs.gov.ru",
          "domain:zakupki.gov.ru",
          "domain:bus.gov.ru",
          "domain:sudrf.ru",
          "domain:kad.arbitr.ru",
          "domain:gov.spb.ru",
          "domain:spb.ru",
          "domain:tatarstan.ru",
          "domain:kzn.ru",
          "domain:youla.ru",
          "domain:lamoda.ru",
          "domain:detmir.ru",
          "domain:dns-shop.ru",
          "domain:citilink.ru",
          "domain:mvideo.ru",
          "domain:eldorado.ru",
          "domain:hoff.ru",
          "domain:lemanapro.ru",
          "domain:drom.ru",
          "domain:auto.ru",
          "domain:drive2.ru",
          "domain:vkusvill.ru",
          "domain:magnit.ru",
          "domain:magnitmarket.ru",
          "domain:lenta.com",
          "domain:perekrestok.ru",
          "domain:5ka.ru",
          "domain:kuper.ru",
          "domain:samokat.ru",
          "domain:delivery-club.ru",
          "domain:chizhik.ru",
          "domain:metro-cc.ru",
          "domain:okko.tv",
          "domain:wink.ru",
          "domain:kion.ru",
          "domain:start.ru",
          "domain:premier.one",
          "domain:more.tv",
          "domain:smotrim.ru",
          "domain:ntv.ru",
          "domain:1tv.ru",
          "domain:matchtv.ru",
          "domain:sportbox.ru",
          "domain:championat.com",
          "domain:sports.ru",
          "domain:rbc.ru",
          "domain:ria.ru",
          "domain:tass.ru",
          "domain:interfax.ru",
          "domain:lenta.ru",
          "domain:fontanka.ru",
          "domain:kp.ru",
          "domain:rg.ru",
          "domain:aif.ru",
          "domain:gazeta.ru",
          "domain:vedomosti.ru",
          "domain:kommersant.ru",
          "domain:iz.ru",
          "domain:mk.ru",
          "domain:rzd-bonus.ru",
          "domain:russianpost.ru",
          "domain:post.ru",
          "domain:pobeda.aero",
          "domain:s7.ru",
          "domain:utair.ru",
          "domain:smartavia.com",
          "domain:azimuth.aero",
          "domain:tutu.ru",
          "domain:aviasales.ru",
          "domain:2gis.com",
          "domain:rabota.ru",
          "domain:superjob.ru",
          "domain:kontur.ru",
          "domain:sbis.ru",
          "domain:diadoc.ru",
          "domain:kontur-extern.ru",
          "domain:rostelecom.ru",
          "domain:rt.ru",
          "domain:mts.ru",
          "domain:beeline.ru",
          "domain:megafon.ru",
          "domain:t2.ru",
          "domain:tele2.ru",
          "domain:yota.ru",
          "domain:dom.ru",
          "domain:ertelecom.ru",
          "domain:ngenix.net",
          "domain:cdnmail.ru",
          "domain:cdnvideo.ru",
          "domain:rambler.ru"
        ],
        "outboundTag": "direct"
      },
      {
        "balancerTag": "balancer",
        "network": "tcp,udp"
      }
    ]
  },
  "stats": {}
}

{"api":{"services":["StatsService"],"tag":"api"},"burstObservatory":{"pingConfig":{"connectivity":"https:\/\/browser.yandex.ru\/generate_204","destination":"https:\/\/www.google.com","httpMethod":"GET","interval":"15s","sampling":4,"timeout":"2s"},"subjectSelector":["proxy"]},"dns":{"disableCache":false,"hosts":{"lkfl2.nalog.ru":["213.24.64.175","213.24.64.17"],"lknpd.nalog.ru":["213.24.64.181"],"safe.dot.dns.yandex.net":["77.88.8.88","77.88.8.2","2a02:6b8::feed:bad","2a02:6b8:0:1::feed:bad"],"security.cloudflare-dns.com":["1.1.1.2","1.0.0.2","2606:4700:4700::1112","2606:4700:4700::1002"]},"queryStrategy":"UseIPv4","serveExpiredTTL":10,"serveStale":true,"servers":["https:\/\/security.cloudflare-dns.com\/dns-query","https+local:\/\/security.cloudflare-dns.com\/dns-query","https+local:\/\/dns.google\/dns-query","tcp+local:\/\/77.88.8.88:53"],"useSystemHosts":true},"inbounds":[{"listen":"127.0.0.1","port":10808,"protocol":"socks","settings":{"auth":"noauth","udp":true,"userLevel":8},"sniffing":{"destOverride":["http","tls","quic"],"enabled":true,"routeOnly":true},"tag":"socks"},{"listen":"127.0.0.1","port":10809,"protocol":"http","settings":{"userLevel":8},"sniffing":{"destOverride":["http","tls","quic"],"enabled":true,"routeOnly":true},"tag":"http"},{"listen":"127.0.0.1","port":11111,"protocol":"dokodemo-door","settings":{"address":"127.0.0.1"},"tag":"metrics_in"},{"listen":"127.0.0.1","port":10085,"protocol":"dokodemo-door","settings":{"address":"127.0.0.1"},"tag":"api_in"}],"log":{"loglevel":"warning"},"meta":null,"metrics":{"tag":"metrics_out"},"outbounds":[{"tag":"proxy-1","protocol":"vless","settings":{"vnext":[{"address":"5.157.10.2","port":443,"users":[{"id":"f88bc31a-c30a-4a7f-bca6-5bc95d5bb593","encryption":"none","level":8,"flow":"xtls-rprx-vision"}]}]},"streamSettings":{"network":"tcp","security":"reality","realitySettings":{"serverName":"sweringa.rottshieldsons.pics","fingerprint":"firefox","publicKey":"x6p656szvu_3CKLsJ4NtkooRvdTVGx7IoPca_p58_jA","shortId":"fb442438e2223836"},"sockopt":{"domainStrategy":"UseIPv4","tcpKeepAliveIdle":60,"tcpKeepAliveInterval":15,"tcpNoDelay":true}}},{"protocol":"freedom","settings":{},"streamSettings":{"sockopt":{"domainStrategy":"UseIPv4","tcpKeepAliveIdle":60,"tcpKeepAliveInterval":15,"tcpNoDelay":true}},"tag":"direct"},{"protocol":"blackhole","tag":"block"}],"policy":{"levels":{"0":{"connIdle":300,"downlinkOnly":1,"handshake":4,"statsUserDownlink":true,"statsUserUplink":true,"uplinkOnly":1},"8":{"connIdle":300,"downlinkOnly":1,"handshake":4,"statsUserDownlink":true,"statsUserUplink":true,"uplinkOnly":1}},"system":{"statsInboundDownlink":true,"statsInboundUplink":true,"statsOutboundDownlink":true,"statsOutboundUplink":true}},"remarks":"🇸🇪 Швеция","routing":{"balancers":[{"selector":["proxy"],"strategy":{"type":"leastPing"},"tag":"balancer"}],"domainStrategy":"AsIs","rules":[{"inboundTag":["metrics_in"],"outboundTag":"metrics_out"},{"inboundTag":["api_in"],"outboundTag":"api"},{"ip":["0.0.0.0\/32","::\/128"],"outboundTag":"block"},{"outboundTag":"block","protocol":["bittorrent"]},{"outboundTag":"block","port":"6881-6889,51413,21413,17417,37305"},{"domain":["domain:oneme.ru","domain:ip.mail.ru","domain:2ip.ru","domain:2ip.io","domain:ipinfo.io","domain:ip-api.com","domain:ipwho.is","domain:api.ipify.org","domain:icanhazip.com","domain:checkip.amazonaws.com","domain:ifconfig.me","domain:ident.me","domain:ipleak.net","domain:dnsleaktest.com","domain:browserleaks.com"],"outboundTag":"block"},{"ip":["0.0.0.0\/8","10.0.0.0\/8","100.64.0.0\/10","127.0.0.0\/8","169.254.0.0\/16","172.16.0.0\/12","192.0.0.0\/24","192.0.2.0\/24","192.88.99.0\/24","192.168.0.0\/16","198.18.0.0\/15","198.51.100.0\/24","203.0.113.0\/24","224.0.0.0\/3","::\/127","fc00::\/7","fe80::\/10","ff00::\/8","224.0.0.0\/4","255.255.255.255"],"outboundTag":"direct"},{"balancerTag":"balancer","ip":["1.1.1.2","1.0.0.2","2606:4700:4700::1112","2606:4700:4700::1002"],"port":443},{"balancerTag":"balancer","domain":["domain:security.cloudflare-dns.com"],"port":443},{"ip":["77.88.8.88","77.88.8.2","2a02:6b8::feed:bad","2a02:6b8:0:1::feed:bad"],"outboundTag":"direct","port":443},{"domain":["domain:safe.dot.dns.yandex.net"],"outboundTag":"direct","port":443},{"outboundTag":"block","protocol":["quic"]},{"balancerTag":"balancer","ip":["149.154.164.0\/22","149.154.160.0\/20","91.108.8.0\/22","91.108.56.0\/22","91.108.4.0\/22","95.161.64.0\/20","149.154.167.0\/24","91.108.16.0\/22","91.108.12.0\/22","91.105.192.0\/23","91.108.20.0\/22","185.76.151.0\/24","149.154.167.0\/20","5.28.128.0\/17"]},{"domain":["domain:push.apple.com","domain:api.push.apple.com","domain:courier.push.apple.com","domain:gateway.push.apple.com","domain:feedback.push.apple.com","domain:mtalk.google.com","domain:fcm.googleapis.com","domain:firebaseinstallations.googleapis.com","domain:firebase.googleapis.com","domain:firebaseappcheck.googleapis.com","domain:android.clients.google.com","domain:push-api.cloud.huawei.com","domain:hms-push-api.cloud.huawei.com","domain:push.xiaomi.com","domain:api.xiaomi.com","domain:push.samsungosp.com","domain:updates.push.services.mozilla.com"],"outboundTag":"direct"},{"domain":["domain:roblox.com","domain:rbxcdn.com","domain:rbx.com","domain:roblox.cn","domain:robloxusercontent.com","domain:robloxapi.com"],"balancerTag":"balancer"},{"balancerTag":"balancer","domain":["domain:t.me","domain:tg.dev","domain:tg.org","domain:tx.me","domain:teleg.xyz","domain:tgcloud.ai","domain:telegram.ai","domain:telegram.asia","domain:telegram.biz","domain:telegram.cloud","domain:telegram.cn","domain:telegram.co","domain:telegram.com","domain:telegram.de","domain:telegram.dev","domain:telegram.dog","domain:telegram.eu","domain:telegram.fr","domain:telegram.host","domain:telegram.in","domain:telegram.info","domain:telegram.io","domain:telegram.jp","domain:telegram.me","domain:telegram.net","domain:telegram.org","domain:telegram.qa","domain:telegram.ru","domain:telegram.services","domain:telegram.solutions","domain:telegram.space","domain:telegram.team","domain:telegram.tech","domain:telegram.uk","domain:telegram.us","domain:telegram.website","domain:telegram.xyz","domain:telegramapp.org","domain:telegra.ph","domain:telesco.pe","domain:nicegram.app","domain:telegramdownload.com","domain:cdn-telegram.org","domain:comments.app","domain:contest.com","domain:fragment.com","domain:graph.org","domain:quiz.directory","domain:tdesktop.com","domain:telega.one","domain:telegram-cdn.org","domain:usercontent.dev","domain:tgram.org","domain:torg.org"]},{"domain":["domain:ru","domain:su","domain:xn--p1ai","domain:yandex.ru","domain:yandex.net","domain:yastatic.net","domain:yandex.com","domain:vk.com","domain:vk.ru","domain:vk.me","domain:userapi.com","domain:vkuseraudio.net","domain:vk-cdn.net","domain:vk-portal.net","domain:ok.ru","domain:mail.ru","domain:my.mail.ru","domain:avito.ru","domain:ozon.ru","domain:wildberries.ru","domain:sberbank.ru","domain:online.sberbank.ru","domain:alfabank.ru","domain:alfa-bank.ru","domain:tbank.ru","domain:tinkoff.ru","domain:vtb.ru","domain:gazprombank.ru","domain:gosuslugi.ru","domain:nalog.ru","domain:mos.ru","domain:mosreg.ru","domain:rzd.ru","domain:pochta.ru","domain:aeroflot.ru","domain:2gis.ru","domain:hh.ru","domain:kinopoisk.ru","domain:ivi.ru","domain:rutube.ru","domain:vkvideo.ru","domain:ya.ru","domain:yandex.by","domain:yandex.kz","domain:yandexcloud.net","domain:yandexcloud.ru","domain:yandex-team.ru","domain:yandex-team.com","domain:yastat.net","domain:yandexmaps.com","domain:yandexmaps.net","domain:yandex.st","domain:dzen.ru","domain:edadeal.ru","domain:toloka.ai","domain:vk.cc","domain:vk.link","domain:vk.team","domain:vk.company","domain:vkuservideo.net","domain:vkuserlive.net","domain:odnoklassniki.ru","domain:odkl.ru","domain:list.ru","domain:inbox.ru","domain:bk.ru","domain:cloud.mail.ru","domain:sber.ru","domain:sberdevices.ru","domain:sberbank.com","domain:sbermarket.ru","domain:alfabank.com","domain:tinkoffjournal.ru","domain:vtb.com","domain:gpb.ru","domain:rshb.ru","domain:psbank.ru","domain:sovcombank.ru","domain:domrf.ru","domain:cbr.ru","domain:banki.ru","domain:yoomoney.ru","domain:yoomoney.com","domain:nspk.ru","domain:mironline.ru","domain:koronapay.com","domain:nalog.gov.ru","domain:sfr.gov.ru","domain:pfr.gov.ru","domain:fssp.gov.ru","domain:rosreestr.gov.ru","domain:pravo.gov.ru","domain:publication.pravo.gov.ru","domain:government.ru","domain:kremlin.ru","domain:minfin.gov.ru","domain:customs.gov.ru","domain:zakupki.gov.ru","domain:bus.gov.ru","domain:sudrf.ru","domain:kad.arbitr.ru","domain:gov.spb.ru","domain:spb.ru","domain:tatarstan.ru","domain:kzn.ru","domain:youla.ru","domain:lamoda.ru","domain:detmir.ru","domain:dns-shop.ru","domain:citilink.ru","domain:mvideo.ru","domain:eldorado.ru","domain:hoff.ru","domain:lemanapro.ru","domain:drom.ru","domain:auto.ru","domain:drive2.ru","domain:vkusvill.ru","domain:magnit.ru","domain:magnitmarket.ru","domain:lenta.com","domain:perekrestok.ru","domain:5ka.ru","domain:kuper.ru","domain:samokat.ru","domain:delivery-club.ru","domain:chizhik.ru","domain:metro-cc.ru","domain:okko.tv","domain:wink.ru","domain:kion.ru","domain:start.ru","domain:premier.one","domain:more.tv","domain:smotrim.ru","domain:ntv.ru","domain:1tv.ru","domain:matchtv.ru","domain:sportbox.ru","domain:championat.com","domain:sports.ru","domain:rbc.ru","domain:ria.ru","domain:tass.ru","domain:interfax.ru","domain:lenta.ru","domain:fontanka.ru","domain:kp.ru","domain:rg.ru","domain:aif.ru","domain:gazeta.ru","domain:vedomosti.ru","domain:kommersant.ru","domain:iz.ru","domain:mk.ru","domain:rzd-bonus.ru","domain:russianpost.ru","domain:post.ru","domain:pobeda.aero","domain:s7.ru","domain:utair.ru","domain:smartavia.com","domain:azimuth.aero","domain:tutu.ru","domain:aviasales.ru","domain:2gis.com","domain:rabota.ru","domain:superjob.ru","domain:kontur.ru","domain:sbis.ru","domain:diadoc.ru","domain:kontur-extern.ru","domain:rostelecom.ru","domain:rt.ru","domain:mts.ru","domain:beeline.ru","domain:megafon.ru","domain:t2.ru","domain:tele2.ru","domain:yota.ru","domain:dom.ru","domain:ertelecom.ru","domain:ngenix.net","domain:cdnmail.ru","domain:cdnvideo.ru","domain:rambler.ru"],"outboundTag":"direct"},{"balancerTag":"balancer","network":"tcp,udp"}]},"stats":{}}

{"api":{"services":["StatsService"],"tag":"api"},"burstObservatory":{"pingConfig":{"connectivity":"https:\/\/browser.yandex.ru\/generate_204","destination":"https:\/\/www.google.com","httpMethod":"GET","interval":"15s","sampling":4,"timeout":"2s"},"subjectSelector":["proxy"]},"dns":{"disableCache":false,"hosts":{"lkfl2.nalog.ru":["213.24.64.175","213.24.64.17"],"lknpd.nalog.ru":["213.24.64.181"],"safe.dot.dns.yandex.net":["77.88.8.88","77.88.8.2","2a02:6b8::feed:bad","2a02:6b8:0:1::feed:bad"],"security.cloudflare-dns.com":["1.1.1.2","1.0.0.2","2606:4700:4700::1112","2606:4700:4700::1002"]},"queryStrategy":"UseIPv4","serveExpiredTTL":10,"serveStale":true,"servers":["https:\/\/security.cloudflare-dns.com\/dns-query","https+local:\/\/security.cloudflare-dns.com\/dns-query","https+local:\/\/dns.google\/dns-query","tcp+local:\/\/77.88.8.88:53"],"useSystemHosts":true},"inbounds":[{"listen":"127.0.0.1","port":10808,"protocol":"socks","settings":{"auth":"noauth","udp":true,"userLevel":8},"sniffing":{"destOverride":["http","tls","quic"],"enabled":true,"routeOnly":true},"tag":"socks"},{"listen":"127.0.0.1","port":10809,"protocol":"http","settings":{"userLevel":8},"sniffing":{"destOverride":["http","tls","quic"],"enabled":true,"routeOnly":true},"tag":"http"},{"listen":"127.0.0.1","port":11111,"protocol":"dokodemo-door","settings":{"address":"127.0.0.1"},"tag":"metrics_in"},{"listen":"127.0.0.1","port":10085,"protocol":"dokodemo-door","settings":{"address":"127.0.0.1"},"tag":"api_in"}],"log":{"loglevel":"warning"},"meta":null,"metrics":{"tag":"metrics_out"},"outbounds":[{"tag":"proxy-1","protocol":"vless","settings":{"vnext":[{"address":"31.77.13.2","port":443,"users":[{"id":"e894c08a-fecc-46f5-bf03-c95d0274c79d","encryption":"none","level":8,"flow":"xtls-rprx-vision"}]}]},"streamSettings":{"network":"tcp","security":"reality","realitySettings":{"serverName":"lesson67.schoolpizorbz.xyz","fingerprint":"firefox","publicKey":"I935dNNphFajETA83ynOilN61A0RRgzoZFF-6pZSu3Q","shortId":"afd0d3b703f1ed70"},"sockopt":{"domainStrategy":"UseIPv4","tcpKeepAliveIdle":60,"tcpKeepAliveInterval":15,"tcpNoDelay":true}}},{"tag":"proxy-2","protocol":"hysteria","settings":{"version":2,"address":"94.249.225.65","port":443},"streamSettings":{"network":"hysteria","security":"tls","method":"hysteria","tlsSettings":{"serverName":"nl1.nuvoryxdata.com"},"hysteriaSettings":{"version":2,"auth":"81f705b5-9039-4adf-8671-783095bba0e8"},"sockopt":{"domainStrategy":"UseIPv4","tcpKeepAliveIdle":60,"tcpKeepAliveInterval":15,"tcpNoDelay":true}}},{"protocol":"freedom","settings":{},"streamSettings":{"sockopt":{"domainStrategy":"UseIPv4","tcpKeepAliveIdle":60,"tcpKeepAliveInterval":15,"tcpNoDelay":true}},"tag":"direct"},{"protocol":"blackhole","tag":"block"}],"policy":{"levels":{"0":{"connIdle":300,"downlinkOnly":1,"handshake":4,"statsUserDownlink":true,"statsUserUplink":true,"uplinkOnly":1},"8":{"connIdle":300,"downlinkOnly":1,"handshake":4,"statsUserDownlink":true,"statsUserUplink":true,"uplinkOnly":1}},"system":{"statsInboundDownlink":true,"statsInboundUplink":true,"statsOutboundDownlink":true,"statsOutboundUplink":true}},"remarks":"🇳🇱 Нидерланды","routing":{"balancers":[{"selector":["proxy"],"strategy":{"type":"leastPing"},"tag":"balancer"}],"domainStrategy":"AsIs","rules":[{"inboundTag":["metrics_in"],"outboundTag":"metrics_out"},{"inboundTag":["api_in"],"outboundTag":"api"},{"ip":["0.0.0.0\/32","::\/128"],"outboundTag":"block"},{"outboundTag":"block","protocol":["bittorrent"]},{"outboundTag":"block","port":"6881-6889,51413,21413,17417,37305"},{"domain":["domain:oneme.ru","domain:ip.mail.ru","domain:2ip.ru","domain:2ip.io","domain:ipinfo.io","domain:ip-api.com","domain:ipwho.is","domain:api.ipify.org","domain:icanhazip.com","domain:checkip.amazonaws.com","domain:ifconfig.me","domain:ident.me","domain:ipleak.net","domain:dnsleaktest.com","domain:browserleaks.com"],"outboundTag":"block"},{"ip":["0.0.0.0\/8","10.0.0.0\/8","100.64.0.0\/10","127.0.0.0\/8","169.254.0.0\/16","172.16.0.0\/12","192.0.0.0\/24","192.0.2.0\/24","192.88.99.0\/24","192.168.0.0\/16","198.18.0.0\/15","198.51.100.0\/24","203.0.113.0\/24","224.0.0.0\/3","::\/127","fc00::\/7","fe80::\/10","ff00::\/8","224.0.0.0\/4","255.255.255.255"],"outboundTag":"direct"},{"balancerTag":"balancer","ip":["1.1.1.2","1.0.0.2","2606:4700:4700::1112","2606:4700:4700::1002"],"port":443},{"balancerTag":"balancer","domain":["domain:security.cloudflare-dns.com"],"port":443},{"ip":["77.88.8.88","77.88.8.2","2a02:6b8::feed:bad","2a02:6b8:0:1::feed:bad"],"outboundTag":"direct","port":443},{"domain":["domain:safe.dot.dns.yandex.net"],"outboundTag":"direct","port":443},{"outboundTag":"block","protocol":["quic"]},{"balancerTag":"balancer","ip":["149.154.164.0\/22","149.154.160.0\/20","91.108.8.0\/22","91.108.56.0\/22","91.108.4.0\/22","95.161.64.0\/20","149.154.167.0\/24","91.108.16.0\/22","91.108.12.0\/22","91.105.192.0\/23","91.108.20.0\/22","185.76.151.0\/24","149.154.167.0\/20","5.28.128.0\/17"]},{"domain":["domain:push.apple.com","domain:api.push.apple.com","domain:courier.push.apple.com","domain:gateway.push.apple.com","domain:feedback.push.apple.com","domain:mtalk.google.com","domain:fcm.googleapis.com","domain:firebaseinstallations.googleapis.com","domain:firebase.googleapis.com","domain:firebaseappcheck.googleapis.com","domain:android.clients.google.com","domain:push-api.cloud.huawei.com","domain:hms-push-api.cloud.huawei.com","domain:push.xiaomi.com","domain:api.xiaomi.com","domain:push.samsungosp.com","domain:updates.push.services.mozilla.com"],"outboundTag":"direct"},{"domain":["domain:roblox.com","domain:rbxcdn.com","domain:rbx.com","domain:roblox.cn","domain:robloxusercontent.com","domain:robloxapi.com"],"balancerTag":"balancer"},{"balancerTag":"balancer","domain":["domain:t.me","domain:tg.dev","domain:tg.org","domain:tx.me","domain:teleg.xyz","domain:tgcloud.ai","domain:telegram.ai","domain:telegram.asia","domain:telegram.biz","domain:telegram.cloud","domain:telegram.cn","domain:telegram.co","domain:telegram.com","domain:telegram.de","domain:telegram.dev","domain:telegram.dog","domain:telegram.eu","domain:telegram.fr","domain:telegram.host","domain:telegram.in","domain:telegram.info","domain:telegram.io","domain:telegram.jp","domain:telegram.me","domain:telegram.net","domain:telegram.org","domain:telegram.qa","domain:telegram.ru","domain:telegram.services","domain:telegram.solutions","domain:telegram.space","domain:telegram.team","domain:telegram.tech","domain:telegram.uk","domain:telegram.us","domain:telegram.website","domain:telegram.xyz","domain:telegramapp.org","domain:telegra.ph","domain:telesco.pe","domain:nicegram.app","domain:telegramdownload.com","domain:cdn-telegram.org","domain:comments.app","domain:contest.com","domain:fragment.com","domain:graph.org","domain:quiz.directory","domain:tdesktop.com","domain:telega.one","domain:telegram-cdn.org","domain:usercontent.dev","domain:tgram.org","domain:torg.org"]},{"domain":["domain:ru","domain:su","domain:xn--p1ai","domain:yandex.ru","domain:yandex.net","domain:yastatic.net","domain:yandex.com","domain:vk.com","domain:vk.ru","domain:vk.me","domain:userapi.com","domain:vkuseraudio.net","domain:vk-cdn.net","domain:vk-portal.net","domain:ok.ru","domain:mail.ru","domain:my.mail.ru","domain:avito.ru","domain:ozon.ru","domain:wildberries.ru","domain:sberbank.ru","domain:online.sberbank.ru","domain:alfabank.ru","domain:alfa-bank.ru","domain:tbank.ru","domain:tinkoff.ru","domain:vtb.ru","domain:gazprombank.ru","domain:gosuslugi.ru","domain:nalog.ru","domain:mos.ru","domain:mosreg.ru","domain:rzd.ru","domain:pochta.ru","domain:aeroflot.ru","domain:2gis.ru","domain:hh.ru","domain:kinopoisk.ru","domain:ivi.ru","domain:rutube.ru","domain:vkvideo.ru","domain:ya.ru","domain:yandex.by","domain:yandex.kz","domain:yandexcloud.net","domain:yandexcloud.ru","domain:yandex-team.ru","domain:yandex-team.com","domain:yastat.net","domain:yandexmaps.com","domain:yandexmaps.net","domain:yandex.st","domain:dzen.ru","domain:edadeal.ru","domain:toloka.ai","domain:vk.cc","domain:vk.link","domain:vk.team","domain:vk.company","domain:vkuservideo.net","domain:vkuserlive.net","domain:odnoklassniki.ru","domain:odkl.ru","domain:list.ru","domain:inbox.ru","domain:bk.ru","domain:cloud.mail.ru","domain:sber.ru","domain:sberdevices.ru","domain:sberbank.com","domain:sbermarket.ru","domain:alfabank.com","domain:tinkoffjournal.ru","domain:vtb.com","domain:gpb.ru","domain:rshb.ru","domain:psbank.ru","domain:sovcombank.ru","domain:domrf.ru","domain:cbr.ru","domain:banki.ru","domain:yoomoney.ru","domain:yoomoney.com","domain:nspk.ru","domain:mironline.ru","domain:koronapay.com","domain:nalog.gov.ru","domain:sfr.gov.ru","domain:pfr.gov.ru","domain:fssp.gov.ru","domain:rosreestr.gov.ru","domain:pravo.gov.ru","domain:publication.pravo.gov.ru","domain:government.ru","domain:kremlin.ru","domain:minfin.gov.ru","domain:customs.gov.ru","domain:zakupki.gov.ru","domain:bus.gov.ru","domain:sudrf.ru","domain:kad.arbitr.ru","domain:gov.spb.ru","domain:spb.ru","domain:tatarstan.ru","domain:kzn.ru","domain:youla.ru","domain:lamoda.ru","domain:detmir.ru","domain:dns-shop.ru","domain:citilink.ru","domain:mvideo.ru","domain:eldorado.ru","domain:hoff.ru","domain:lemanapro.ru","domain:drom.ru","domain:auto.ru","domain:drive2.ru","domain:vkusvill.ru","domain:magnit.ru","domain:magnitmarket.ru","domain:lenta.com","domain:perekrestok.ru","domain:5ka.ru","domain:kuper.ru","domain:samokat.ru","domain:delivery-club.ru","domain:chizhik.ru","domain:metro-cc.ru","domain:okko.tv","domain:wink.ru","domain:kion.ru","domain:start.ru","domain:premier.one","domain:more.tv","domain:smotrim.ru","domain:ntv.ru","domain:1tv.ru","domain:matchtv.ru","domain:sportbox.ru","domain:championat.com","domain:sports.ru","domain:rbc.ru","domain:ria.ru","domain:tass.ru","domain:interfax.ru","domain:lenta.ru","domain:fontanka.ru","domain:kp.ru","domain:rg.ru","domain:aif.ru","domain:gazeta.ru","domain:vedomosti.ru","domain:kommersant.ru","domain:iz.ru","domain:mk.ru","domain:rzd-bonus.ru","domain:russianpost.ru","domain:post.ru","domain:pobeda.aero","domain:s7.ru","domain:utair.ru","domain:smartavia.com","domain:azimuth.aero","domain:tutu.ru","domain:aviasales.ru","domain:2gis.com","domain:rabota.ru","domain:superjob.ru","domain:kontur.ru","domain:sbis.ru","domain:diadoc.ru","domain:kontur-extern.ru","domain:rostelecom.ru","domain:rt.ru","domain:mts.ru","domain:beeline.ru","domain:megafon.ru","domain:t2.ru","domain:tele2.ru","domain:yota.ru","domain:dom.ru","domain:ertelecom.ru","domain:ngenix.net","domain:cdnmail.ru","domain:cdnvideo.ru","domain:rambler.ru"],"outboundTag":"direct"},{"balancerTag":"balancer","network":"tcp,udp"}]},"stats":{}}

{
  "api": {
    "services": [
      "StatsService"
    ],
    "tag": "api"
  },
  "burstObservatory": {
    "pingConfig": {
      "connectivity": "https:\/\/browser.yandex.ru\/generate_204",
      "destination": "https:\/\/www.google.com",
      "httpMethod": "GET",
      "interval": "15s",
      "sampling": 4,
      "timeout": "2s"
    },
    "subjectSelector": [
      "proxy"
    ]
  },
  "dns": {
    "disableCache": false,
    "hosts": {
      "lkfl2.nalog.ru": [
        "213.24.64.175",
        "213.24.64.17"
      ],
      "lknpd.nalog.ru": [
        "213.24.64.181"
      ],
      "safe.dot.dns.yandex.net": [
        "77.88.8.88",
        "77.88.8.2",
        "2a02:6b8::feed:bad",
        "2a02:6b8:0:1::feed:bad"
      ],
      "security.cloudflare-dns.com": [
        "1.1.1.2",
        "1.0.0.2",
        "2606:4700:4700::1112",
        "2606:4700:4700::1002"
      ]
    },
    "queryStrategy": "UseIPv4",
    "serveExpiredTTL": 10,
    "serveStale": true,
    "servers": [
      "https:\/\/security.cloudflare-dns.com\/dns-query",
      "https+local:\/\/security.cloudflare-dns.com\/dns-query",
      "https+local:\/\/dns.google\/dns-query",
      "tcp+local:\/\/77.88.8.88:53"
    ],
    "useSystemHosts": true
  },
  "inbounds": [
    {
      "listen": "127.0.0.1",
      "port": 10808,
      "protocol": "socks",
      "settings": {
        "auth": "noauth",
        "udp": true,
        "userLevel": 8
      },
      "sniffing": {
        "destOverride": [
          "http",
          "tls",
          "quic"
        ],
        "enabled": true,
        "routeOnly": true
      },
      "tag": "socks"
    },
    {
      "listen": "127.0.0.1",
      "port": 10809,
      "protocol": "http",
      "settings": {
        "userLevel": 8
      },
      "sniffing": {
        "destOverride": [
          "http",
          "tls",
          "quic"
        ],
        "enabled": true,
        "routeOnly": true
      },
      "tag": "http"
    },
    {
      "listen": "127.0.0.1",
      "port": 11111,
      "protocol": "dokodemo-door",
      "settings": {
        "address": "127.0.0.1"
      },
      "tag": "metrics_in"
    },
    {
      "listen": "127.0.0.1",
      "port": 10085,
      "protocol": "dokodemo-door",
      "settings": {
        "address": "127.0.0.1"
      },
      "tag": "api_in"
    }
  ],
  "log": {
    "loglevel": "warning"
  },
  "meta": null,
  "metrics": {
    "tag": "metrics_out"
  },
  "outbounds": [
    {
      "tag": "proxy-1",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "196.198.111.189",
            "port": 8443,
            "users": [
              {
                "id": "f121ffc8-f6dc-4728-a871-a05e3f9cf8c5",
                "encryption": "none",
                "level": 8,
                "flow": "xtls-rprx-vision"
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "tcp",
        "security": "tls",
        "tlsSettings": {
          "serverName": "usr-6b09ce88-api-v3.alcors.net",
          "fingerprint": "firefox"
        },
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      }
    },
    {
      "protocol": "freedom",
      "settings": {},
      "streamSettings": {
        "sockopt": {
          "domainStrategy": "UseIPv4",
          "tcpKeepAliveIdle": 60,
          "tcpKeepAliveInterval": 15,
          "tcpNoDelay": true
        }
      },
      "tag": "direct"
    },
    {
      "protocol": "blackhole",
      "tag": "block"
    }
  ],
  "policy": {
    "levels": {
      "0": {
        "connIdle": 300,
        "downlinkOnly": 1,
        "handshake": 4,
        "statsUserDownlink": true,
        "statsUserUplink": true,
        "uplinkOnly": 1
      },
      "8": {
        "connIdle": 300,
        "downlinkOnly": 1,
        "handshake": 4,
        "statsUserDownlink": true,
        "statsUserUplink": true,
        "uplinkOnly": 1
      }
    },
    "system": {
      "statsInboundDownlink": true,
      "statsInboundUplink": true,
      "statsOutboundDownlink": true,
      "statsOutboundUplink": true
    }
  },
  "remarks": "🇰🇿 Казахстан",
  "routing": {
    "balancers": [
      {
        "selector": [
          "proxy"
        ],
        "strategy": {
          "type": "leastPing"
        },
        "tag": "balancer"
      }
    ],
    "domainStrategy": "AsIs",
    "rules": [
      {
        "inboundTag": [
          "metrics_in"
        ],
        "outboundTag": "metrics_out"
      },
      {
        "inboundTag": [
          "api_in"
        ],
        "outboundTag": "api"
      },
      {
        "ip": [
          "0.0.0.0\/32",
          "::\/128"
        ],
        "outboundTag": "block"
      },
      {
        "outboundTag": "block",
        "protocol": [
          "bittorrent"
        ]
      },
      {
        "outboundTag": "block",
        "port": "6881-6889,51413,21413,17417,37305"
      },
      {
        "domain": [
          "domain:oneme.ru",
          "domain:ip.mail.ru",
          "domain:2ip.ru",
          "domain:2ip.io",
          "domain:ipinfo.io",
          "domain:ip-api.com",
          "domain:ipwho.is",
          "domain:api.ipify.org",
          "domain:icanhazip.com",
          "domain:checkip.amazonaws.com",
          "domain:ifconfig.me",
          "domain:ident.me",
          "domain:ipleak.net",
          "domain:dnsleaktest.com",
          "domain:browserleaks.com"
        ],
        "outboundTag": "block"
      },
      {
        "ip": [
          "0.0.0.0\/8",
          "10.0.0.0\/8",
          "100.64.0.0\/10",
          "127.0.0.0\/8",
          "169.254.0.0\/16",
          "172.16.0.0\/12",
          "192.0.0.0\/24",
          "192.0.2.0\/24",
          "192.88.99.0\/24",
          "192.168.0.0\/16",
          "198.18.0.0\/15",
          "198.51.100.0\/24",
          "203.0.113.0\/24",
          "224.0.0.0\/3",
          "::\/127",
          "fc00::\/7",
          "fe80::\/10",
          "ff00::\/8",
          "224.0.0.0\/4",
          "255.255.255.255"
        ],
        "outboundTag": "direct"
      },
      {
        "balancerTag": "balancer",
        "ip": [
          "1.1.1.2",
          "1.0.0.2",
          "2606:4700:4700::1112",
          "2606:4700:4700::1002"
        ],
        "port": 443
      },
      {
        "balancerTag": "balancer",
        "domain": [
          "domain:security.cloudflare-dns.com"
        ],
        "port": 443
      },
      {
        "ip": [
          "77.88.8.88",
          "77.88.8.2",
          "2a02:6b8::feed:bad",
          "2a02:6b8:0:1::feed:bad"
        ],
        "outboundTag": "direct",
        "port": 443
      },
      {
        "domain": [
          "domain:safe.dot.dns.yandex.net"
        ],
        "outboundTag": "direct",
        "port": 443
      },
      {
        "outboundTag": "block",
        "protocol": [
          "quic"
        ]
      },
      {
        "balancerTag": "balancer",
        "ip": [
          "149.154.164.0\/22",
          "149.154.160.0\/20",
          "91.108.8.0\/22",
          "91.108.56.0\/22",
          "91.108.4.0\/22",
          "95.161.64.0\/20",
          "149.154.167.0\/24",
          "91.108.16.0\/22",
          "91.108.12.0\/22",
          "91.105.192.0\/23",
          "91.108.20.0\/22",
          "185.76.151.0\/24",
          "149.154.167.0\/20",
          "5.28.128.0\/17"
        ]
      },
      {
        "domain": [
          "domain:push.apple.com",
          "domain:api.push.apple.com",
          "domain:courier.push.apple.com",
          "domain:gateway.push.apple.com",
          "domain:feedback.push.apple.com",
          "domain:mtalk.google.com",
          "domain:fcm.googleapis.com",
          "domain:firebaseinstallations.googleapis.com",
          "domain:firebase.googleapis.com",
          "domain:firebaseappcheck.googleapis.com",
          "domain:android.clients.google.com",
          "domain:push-api.cloud.huawei.com",
          "domain:hms-push-api.cloud.huawei.com",
          "domain:push.xiaomi.com",
          "domain:api.xiaomi.com",
          "domain:push.samsungosp.com",
          "domain:updates.push.services.mozilla.com"
        ],
        "outboundTag": "direct"
      },
      {
        "domain": [
          "domain:roblox.com",
          "domain:rbxcdn.com",
          "domain:rbx.com",
          "domain:roblox.cn",
          "domain:robloxusercontent.com",
          "domain:robloxapi.com"
        ],
        "balancerTag": "balancer"
      },
      {
        "balancerTag": "balancer",
        "domain": [
          "domain:t.me",
          "domain:tg.dev",
          "domain:tg.org",
          "domain:tx.me",
          "domain:teleg.xyz",
          "domain:tgcloud.ai",
          "domain:telegram.ai",
          "domain:telegram.asia",
          "domain:telegram.biz",
          "domain:telegram.cloud",
          "domain:telegram.cn",
          "domain:telegram.co",
          "domain:telegram.com",
          "domain:telegram.de",
          "domain:telegram.dev",
          "domain:telegram.dog",
          "domain:telegram.eu",
          "domain:telegram.fr",
          "domain:telegram.host",
          "domain:telegram.in",
          "domain:telegram.info",
          "domain:telegram.io",
          "domain:telegram.jp",
          "domain:telegram.me",
          "domain:telegram.net",
          "domain:telegram.org",
          "domain:telegram.qa",
          "domain:telegram.ru",
          "domain:telegram.services",
          "domain:telegram.solutions",
          "domain:telegram.space",
          "domain:telegram.team",
          "domain:telegram.tech",
          "domain:telegram.uk",
          "domain:telegram.us",
          "domain:telegram.website",
          "domain:telegram.xyz",
          "domain:telegramapp.org",
          "domain:telegra.ph",
          "domain:telesco.pe",
          "domain:nicegram.app",
          "domain:telegramdownload.com",
          "domain:cdn-telegram.org",
          "domain:comments.app",
          "domain:contest.com",
          "domain:fragment.com",
          "domain:graph.org",
          "domain:quiz.directory",
          "domain:tdesktop.com",
          "domain:telega.one",
          "domain:telegram-cdn.org",
          "domain:usercontent.dev",
          "domain:tgram.org",
          "domain:torg.org"
        ]
      },
      {
        "domain": [
          "domain:ru",
          "domain:su",
          "domain:xn--p1ai",
          "domain:yandex.ru",
          "domain:yandex.net",
          "domain:yastatic.net",
          "domain:yandex.com",
          "domain:vk.com",
          "domain:vk.ru",
          "domain:vk.me",
          "domain:userapi.com",
          "domain:vkuseraudio.net",
          "domain:vk-cdn.net",
          "domain:vk-portal.net",
          "domain:ok.ru",
          "domain:mail.ru",
          "domain:my.mail.ru",
          "domain:avito.ru",
          "domain:ozon.ru",
          "domain:wildberries.ru",
          "domain:sberbank.ru",
          "domain:online.sberbank.ru",
          "domain:alfabank.ru",
          "domain:alfa-bank.ru",
          "domain:tbank.ru",
          "domain:tinkoff.ru",
          "domain:vtb.ru",
          "domain:gazprombank.ru",
          "domain:gosuslugi.ru",
          "domain:nalog.ru",
          "domain:mos.ru",
          "domain:mosreg.ru",
          "domain:rzd.ru",
          "domain:pochta.ru",
          "domain:aeroflot.ru",
          "domain:2gis.ru",
          "domain:hh.ru",
          "domain:kinopoisk.ru",
          "domain:ivi.ru",
          "domain:rutube.ru",
          "domain:vkvideo.ru",
          "domain:ya.ru",
          "domain:yandex.by",
          "domain:yandex.kz",
          "domain:yandexcloud.net",
          "domain:yandexcloud.ru",
          "domain:yandex-team.ru",
          "domain:yandex-team.com",
          "domain:yastat.net",
          "domain:yandexmaps.com",
          "domain:yandexmaps.net",
          "domain:yandex.st",
          "domain:dzen.ru",
          "domain:edadeal.ru",
          "domain:toloka.ai",
          "domain:vk.cc",
          "domain:vk.link",
          "domain:vk.team",
          "domain:vk.company",
          "domain:vkuservideo.net",
          "domain:vkuserlive.net",
          "domain:odnoklassniki.ru",
          "domain:odkl.ru",
          "domain:list.ru",
          "domain:inbox.ru",
          "domain:bk.ru",
          "domain:cloud.mail.ru",
          "domain:sber.ru",
          "domain:sberdevices.ru",
          "domain:sberbank.com",
          "domain:sbermarket.ru",
          "domain:alfabank.com",
          "domain:tinkoffjournal.ru",
          "domain:vtb.com",
          "domain:gpb.ru",
          "domain:rshb.ru",
          "domain:psbank.ru",
          "domain:sovcombank.ru",
          "domain:domrf.ru",
          "domain:cbr.ru",
          "domain:banki.ru",
          "domain:yoomoney.ru",
          "domain:yoomoney.com",
          "domain:nspk.ru",
          "domain:mironline.ru",
          "domain:koronapay.com",
          "domain:nalog.gov.ru",
          "domain:sfr.gov.ru",
          "domain:pfr.gov.ru",
          "domain:fssp.gov.ru",
          "domain:rosreestr.gov.ru",
          "domain:pravo.gov.ru",
          "domain:publication.pravo.gov.ru",
          "domain:government.ru",
          "domain:kremlin.ru",
          "domain:minfin.gov.ru",
          "domain:customs.gov.ru",
          "domain:zakupki.gov.ru",
          "domain:bus.gov.ru",
          "domain:sudrf.ru",
          "domain:kad.arbitr.ru",
          "domain:gov.spb.ru",
          "domain:spb.ru",
          "domain:tatarstan.ru",
          "domain:kzn.ru",
          "domain:youla.ru",
          "domain:lamoda.ru",
          "domain:detmir.ru",
          "domain:dns-shop.ru",
          "domain:citilink.ru",
          "domain:mvideo.ru",
          "domain:eldorado.ru",
          "domain:hoff.ru",
          "domain:lemanapro.ru",
          "domain:drom.ru",
          "domain:auto.ru",
          "domain:drive2.ru",
          "domain:vkusvill.ru",
          "domain:magnit.ru",
          "domain:magnitmarket.ru",
          "domain:lenta.com",
          "domain:perekrestok.ru",
          "domain:5ka.ru",
          "domain:kuper.ru",
          "domain:samokat.ru",
          "domain:delivery-club.ru",
          "domain:chizhik.ru",
          "domain:metro-cc.ru",
          "domain:okko.tv",
          "domain:wink.ru",
          "domain:kion.ru",
          "domain:start.ru",
          "domain:premier.one",
          "domain:more.tv",
          "domain:smotrim.ru",
          "domain:ntv.ru",
          "domain:1tv.ru",
          "domain:matchtv.ru",
          "domain:sportbox.ru",
          "domain:championat.com",
          "domain:sports.ru",
          "domain:rbc.ru",
          "domain:ria.ru",
          "domain:tass.ru",
          "domain:interfax.ru",
          "domain:lenta.ru",
          "domain:fontanka.ru",
          "domain:kp.ru",
          "domain:rg.ru",
          "domain:aif.ru",
          "domain:gazeta.ru",
          "domain:vedomosti.ru",
          "domain:kommersant.ru",
          "domain:iz.ru",
          "domain:mk.ru",
          "domain:rzd-bonus.ru",
          "domain:russianpost.ru",
          "domain:post.ru",
          "domain:pobeda.aero",
          "domain:s7.ru",
          "domain:utair.ru",
          "domain:smartavia.com",
          "domain:azimuth.aero",
          "domain:tutu.ru",
          "domain:aviasales.ru",
          "domain:2gis.com",
          "domain:rabota.ru",
          "domain:superjob.ru",
          "domain:kontur.ru",
          "domain:sbis.ru",
          "domain:diadoc.ru",
          "domain:kontur-extern.ru",
          "domain:rostelecom.ru",
          "domain:rt.ru",
          "domain:mts.ru",
          "domain:beeline.ru",
          "domain:megafon.ru",
          "domain:t2.ru",
          "domain:tele2.ru",
          "domain:yota.ru",
          "domain:dom.ru",
          "domain:ertelecom.ru",
          "domain:ngenix.net",
          "domain:cdnmail.ru",
          "domain:cdnvideo.ru",
          "domain:rambler.ru"
        ],
        "outboundTag": "direct"
      },
      {
        "balancerTag": "balancer",
        "network": "tcp,udp"
      }
    ]
  },
  "stats": {}
}

vless://f88bc31a-c30a-4a7f-bca6-5bc95d5bb593@sweringa.rottshieldsons.pics:443?flow=xtls-rprx-vision&type=tcp&security=reality&fp=firefox&sni=sweringa.rottshieldsons.pics&pbk=x6p656szvu_3CKLsJ4NtkooRvdTVGx7IoPca_p58_jA&sid=fb442438e2223836#%F0%9F%87%B8%F0%9F%87%AA+%D0%A8%D0%B2%D0%B5%D1%86%D0%B8%D1%8F+%232

vless://8548b395-5ddd-43b4-886a-9473e43605da@104.18.3.64:443?type=grpc&security=tls&fp=firefox&sni=a1257.kqpgfib.store&serviceName=4855af74b778699bbf6721ab2019229d280f1281#%F0%9F%87%B3%F0%9F%87%B1+%D0%9D%D0%B8%D0%B4%D0%B5%D1%80%D0%BB%D0%B0%D0%BD%D0%B4%D1%8B+%233

vless://e894c08a-fecc-46f5-bf03-c95d0274c79d@31.77.13.2:443?flow=xtls-rprx-vision&type=tcp&security=reality&fp=firefox&sni=lesson67.schoolpizorbz.xyz&pbk=I935dNNphFajETA83ynOilN61A0RRgzoZFF-6pZSu3Q&sid=afd0d3b703f1ed70#%F0%9F%87%B3%F0%9F%87%B1+%D0%9D%D0%B8%D0%B4%D0%B5%D1%80%D0%BB%D0%B0%D0%BD%D0%B4%D1%8B+%231
vless://56dec3ac-1a96-42e9-ad06-6d4219798fb3@189.74.116.8:443?flow=xtls-rprx-vision&type=tcp&security=reality&fp=firefox&sni=api.mediatropa.cc&pbk=r5WB5FnSCt4eeBC1FJMfkWHbzsMuabo0Rc6wuAhlZUs&sid=a8#%F0%9F%87%AB%F0%9F%87%B7+%D0%90%D0%B2%D1%82%D0%BE%D0%BF%D0%BE%D0%B4%D0%B1%D0%BE%D1%80
vless://e460e7b2-a146-4468-87ed-52510b2caae6@168.113.255.166:9872?type=grpc&security=reality&fp=qq&sni=dl.google.com&pbk=sm3E3hjmT6_Gmg_O9rBz4nfXYrHpnl6-LvcCp6T6_xc&sid=aa&serviceName=grpc-tunnel#%D0%93%D0%BB%D1%83%D1%88%D0%B8%D0%BB%D0%BA%D0%B0+%7C+%D0%A0%D0%BE%D1%81%D1%81%D0%B8%D1%8F+%2302
vless://f88bc31a-c30a-4a7f-bca6-5bc95d5bb593@5.157.10.2:443?flow=xtls-rprx-vision&type=tcp&security=reality&fp=firefox&sni=sweringa.rottshieldsons.pics&pbk=x6p656szvu_3CKLsJ4NtkooRvdTVGx7IoPca_p58_jA&sid=fb442438e2223836#%D0%93%D0%BB%D1%83%D1%88%D0%B8%D0%BB%D0%BA%D0%B0+%7C+%D0%A8%D0%B2%D0%B5%D1%86%D0%B8%D1%8F+%2301
vless://bc0f9e3a-6dad-42d5-b09f-dff4cdf57437@170.114.45.6:443?type=ws&security=tls&fp=firefox&sni=googleapis.hmacreation.eu.cc&host=googleapis.hmacreation.eu.cc#%F0%9F%87%B8%F0%9F%87%AC+%D0%A1%D0%B8%D0%BD%D0%B3%D0%B0%D0%BF%D1%83%D1%80+%232
vless://8548b395-5ddd-43b4-886a-9473e43605da@104.18.3.64:443?type=grpc&security=tls&fp=firefox&sni=a1257.kqpgfib.store&serviceName=4855af74b778699bbf6721ab2019229d280f1281#%F0%9F%87%B3%F0%9F%87%B1+%D0%9D%D0%B8%D0%B4%D0%B5%D1%80%D0%BB%D0%B0%D0%BD%D0%B4%D1%8B+%233


[Interface]
Address = 172.16.0.2/32
Address = 2606:4700:110:82a4:d3d0:b3f2:c570:86a6/128
PrivateKey = UEXdJSb3f/b8sb7Om6zXhpDnUktuK1gExeCMtOCc51c=
MTU = 1280
Jc = 4
Jmin = 40
Jmax = 70
H1 = 1
H2 = 2
H3 = 3
H4 = 4
I1 = <b 0xc2000000011419fa4bb3599f336777de79f81ca9a8d80d91eeec000044c635cef024a885dcb66d1420a91a8c427e87d6cf8e08b563932f449412cddf77d3e2594ea1c7a183c238a89e9adb7ffa57c133e55c59bec101634db90afb83f75b19fe703179e26a31902324c73f82d9354e1ed8da39af610afcb27e6590a44341a0828e5a3d2f0e0f7b0945d7bf3402feea0ee6332e19bdf48ffc387a97227aa97b205a485d282cd66d1c384bafd63dc42f822c4df2109db5b5646c458236ddcc01ae1c493482128bc0830c9e1233f0027a0d262f92b49d9d8abd9a9e0341f6e1214761043c021d7aa8c464b9d865f5fbe234e49626e00712031703a3e23ef82975f014ee1e1dc428521dc23ce7c6c13663b19906240b3efe403cf30559d798871557e4e60e86c29ea4504ed4d9bb8b549d0e8acd6c334c39bb8fb42ede68fb2aadf00cfc8bcc12df03602bbd4fe701d64a39f7ced112951a83b1dbbe6cd696dd3f15985c1b9fef72fa8d0319708b633cc4681910843ce753fac596ed9945d8b839aeff8d3bf0449197bd0bb22ab8efd5d63eb4a95db8d3ffc796ed5bcf2f4a136a8a36c7a0c65270d511aebac733e61d414050088a1c3d868fb52bc7e57d3d9fd132d78b740a6ecdc6c24936e92c28672dbe00928d89b891865f885aeb4c4996d50c2bbbb7a99ab5de02ac89b3308e57bcecf13f2da0333d1420e18b66b4c23d625d836b538fc0c221d6bd7f566a31fa292b85be96041d8e0bfe655d5dc1afed23eb8f2b3446561bbee7644325cc98d31cea38b865bdcc507e48c6ebdc7553be7bd6ab963d5a14615c4b81da7081c127c791224853e2d19bafdc0d9f3f3a6de898d14abb0e2bc849917e0a599ed4a541268ad0e60ea4d147dc33d17fa82f22aa505ccb53803a31d10a7ca2fea0b290a52ee92c7bf4aab7cea4e3c07b1989364eed87a3c6ba65188cd349d37ce4eefde9ec43bab4b4dc79e03469c2ad6b902e28e0bbbbf696781ad4edf424ffb35ce0236d373629008f142d04b5e08a124237e03e3149f4cdde92d7fae581a1ac332e26b2c9c1a6bdec5b3a9c7a2a870f7a0c25fc6ce245e029b686e346c6d862ad8df6d9b62474fbc31dbb914711f78074d4441f4e6e9edca3c52315a5c0653856e23f681558d669f4a4e6915bcf42b56ce36cb7dd3983b0b1d6fdf0f8efddb68e7ca0ae9dd4570fe6978fbb524109f6ec957ca61f1767ef74eb803b0f16abd0087cf2d01bc1db1c01d97ac81b3196c934586963fe7cf2d310e0739621e8bd00dc23fded18576d8c8f285d7bb5f43b547af3c76235de8b6f757f817683b2151600b11721219212bf27558edd439e73fce951f61d582320e5f4d6c315c71129b719277fc144bbe8ded25ab6d29b6e189c9bd9b16538faf60cc2aab3c3bb81fc2213657f2dd0ceb9b3b871e1423d8d3e8cc008721ef03b28e0ee7bb66b8f2a2ac01ef88df1f21ed49bf1ce435df31ac34485936172567488812429c269b49ee9e3d99652b51a7a614b7c460bf0d2d64d8349ded7345bedab1ea0a766a8470b1242f38d09f7855a32db39516c2bd4bcc538c52fa3a90c8714d4b006a15d9c7a7d04919a1cab48da7cce0d5de1f9e5f8936cffe469132991c6eb84c5191d1bcf69f70c58d9a7b66846440a9f0eef25ee6ab62715b50ca7bef0bc3013d4b62e1639b5028bdf757454356e9326a4c76dabfb497d451a3a1d2dbd46ec283d255799f72dfe878ae25892e25a2542d3ca9018394d8ca35b53ccd94947a8>

[Peer]
PublicKey = bmXOC+F1FxEMF9dyiK2H5/1SUtzH0JuVo51h2wPfgyo=
Endpoint = 162.159.192.7:4500
AllowedIPs = 0.0.0.0/0, ::/0
PersistentKeepalive = 25


vless://00000000-0000-0001-0000-000000000000@api.14887277.xyz:443?type=ws&security=tls&fp=chrome&sni=trx.tools&path=%2Fsession&host=api.14887277.xyz&alpn=http/1.1#%F0%9F%87%B7%F0%9F%87%BA+%D0%A2%D0%B5%D0%BB%D0%B5%D0%B3%D1%80%D0%B0%D0%BC+%F0%9F%8E%84+%28telegram-only%29
vless://1ade7da3-edbe-4e1d-acd3-9738379a0dac@nl-06.avroraservice.online:8443?type=xhttp&security=reality&fp=safari&sni=cdn-nl.cahmes.space&pbk=R3xeImGP5Bsx42LkRruIs3vIKHnPVR9aodbouAiemzM&sid=d73a212e98084d3b&path=%2Fxhttp&mode=stream-one#%F0%9F%87%B3%F0%9F%87%B1+%D0%9D%D0%B8%D0%B4%D0%B5%D1%80%D0%BB%D0%B0%D0%BD%D0%B4%D1%8B+%F0%9F%90%8C+Youtube+%F0%9F%93%BA
hysteria2://f88bc31a-c30a-4a7f-bca6-5bc95d5bb593@88.119.176.54:443?sni=tuv10.harcho.shop&alpn=h3#%F0%9F%87%B1%F0%9F%87%B9%20%D0%9B%D0%B8%D1%82%D0%B2%D0%B0%20%5B%23%D0%A0%D0%9A%D0%9F%5D
ss://MjAyMi1ibGFrZTMtY2hhY2hhMjAtcG9seTEzMDU6OHlPM0FOV2VmdXVHczFsUktYRUNRQTFGRWh4bFdGVjJwcFFNY0JhWm81WT0@47.254.143.169:443#%F0%9F%87%A9%F0%9F%87%AA%20%D0%93%D0%B5%D1%80%D0%BC%D0%B0%D0%BD%D0%B8%D1%8F%20%5B%23%D0%A0%D0%9A%D0%9F%5D
vless://c53ea5e9-ed8b-4990-805d-7f1d6451426c@83.243.86.215:8443?flow=xtls-rprx-vision&security=reality&sni=durov.sky-vault.top&fp=firefox&pbk=fSVfR9NB-6J6smrZlavi0GWd8JfDh0aXuEkKbtuFzUI&sid=3cbc3d737fb9c4af#%F0%9F%87%B5%F0%9F%87%B1%20%D0%9F%D0%BE%D0%BB%D1%8C%D1%88%D0%B0%20%7C%20%F0%9F%94%97%20%D0%9A%D0%B0%D1%81%D0%BA%D0%B0%D0%B4%20%5B%23%D0%A0%D0%9A%D0%9F%5D
vless://5db72264-1d45-0068-8f7e-d1574b43008e@89.223.17.67:443?flow=xtls-rprx-vision&security=reality&sni=nohope-67-s4.mcdeliver.ru&fp=edge&pbk=Aj6Lfc0JKKROX46eHAQHlzrNpOTY9CKp7BcVj9cw8Ag&sid=75f8575e5396a2fe#%F0%9F%87%B8%F0%9F%87%AA%20%D0%A8%D0%B2%D0%B5%D1%86%D0%B8%D1%8F%20%7C%20%F0%9F%94%97%20%D0%9A%D0%B0%D1%81%D0%BA%D0%B0%D0%B4%20%5B%23%D0%A0%D0%9A%D0%9F%5D
vless://2a7bf1d0-c4ef-43a6-b62a-22821db65b5e@50.7.154.74:443?flow=xtls-rprx-vision&security=reality&sni=api.mediasvyaz.cc&fp=firefox&pbk=r5WB5FnSCt4eeBC1FJMfkWHbzsMuabo0Rc6wuAhlZUs&sid=a8#%F0%9F%87%AC%F0%9F%87%A7%20%D0%92%D0%B5%D0%BB%D0%B8%D0%BA%D0%BE%D0%B1%D1%80%D0%B8%D1%82%D0%B0%D0%BD%D0%B8%D1%8F%20%7C%20%F0%9F%94%97%20%D0%9A%D0%B0%D1%81%D0%BA%D0%B0%D0%B4%20%5B%23%D0%A0%D0%9A%D0%9F%5D
