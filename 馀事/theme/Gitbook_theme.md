# Gitbook_theme

Gitbook's `book.json` 文件

## theme-fexa

```
{
    "plugins": [
        "-sharing",
        "-fontsettings",
        "back-to-top-button",
        "copy-code-button",
        "cuav-chapters",
        "heading-anchors",
        "theme-fexa"
    ],
    "variables": {
        "themeFexa": {
            "nav": [{
                "url": "http://...",
                "target": "_blank",
                "name": "简易教程"
            }]
        }
    },
    "pluginsConfig": {
        "theme-fexa": {
            "search-placeholder": "输入关键字搜索",
            "logo": "./logo.png",
            "favicon": "./favicon.ico"
        }
    }
}
```

## theme-fexa-black

```
{
    "plugins": [
        "-sharing",
        "-fontsettings",
        "back-to-top-button",
        "copy-code-button",
        "cuav-chapters",
        "heading-anchors",
        "theme-fexa-black",
        "lightbox"
    ],
    "variables": {
        "themeFexa": {
            "showHome": false,
            "showNavigator": false,
            "nav": [{
                    "url": "http://...",
                    "target": "_blank",
                    "name": "解决方案"
                },
                {
                    "url": "http://...",
                    "target": "_blank",
                    "name": "产品中心"
                },
                {
                    "url": "http://...",
                    "target": "_blank",
                    "name": "开发者文档"
                },
                {
                    "url": "http://...",
                    "target": "_blank",
                    "name": "管理控制台",
                    "border": "nav-border",
                    "type": "console"
                }
            ]
        }
    },
    "pluginsConfig": {
        "theme-fexa": {
            "search-placeholder": "输入关键字搜索",
            "logo": "./assets/logo.png",
            "favicon": "./assets/favicon.ico"
        }
    }
}
```

## theme-PeiQi

```
{
    "title": "PeiQi WiKi文库",
    "author": "PeiQi",
    "description": "WiKi文库",
    "language": "zh-hans",

    "plugins": [
        "back-to-top-button",
        "expandable-chapters",
        "theme-comscore",
        "splitter",
        "alerts",
        "chapter-fold",
        "code",
        "github",
        "favicon",
        "accordion",
        "-lunr",
        "-search",
        "search-pro",
        "emphasize",
        "-sharing",
        "sharing-plus",
        "tbfed-pagefooter",
        "lightbox",
        "flexible-alerts",
        "pageview-count"
    ],
    "pluginsConfig": {
        "github": {
            "url": "https://github.com/PeiQi0"
        },
        "tbfed-pagefooter": {
            "copyright": "PeiQi WiKi文库",
            "modify_label": "文件更新时间：",
            "modify_format": "YYYY-MM-DD HH:mm:ss"
        }

    }
}
```

## theme-snowdreams1006

```
{
    "title": "雪之梦技术驿站",
    "author": "snowdreams1006",
    "description": "雪之梦技术驿站,snowdreams1006 搭建的 Gitbook 个人博客,详情请访问 https://snowdreams1006.github.io/",
    "language": "zh-hans",
    "gitbook": "3.2.3",
    "links": {
        "sidebar": {
            "技术博客": "https://blog.snowdreams1006.cn/"
        }
    },
    "plugins": [
        "toc",
        "-lunr",
        "-search",
        "search-plus",
        "splitter",
        "-sharing",
        "sharing-plus",
        "expandable-chapters-small",
        "anchor-navigation-ex",
        "edit-link-plus",
        "code",
        "chart",
        "favicon-absolute",
        "github-buttons",
        "advanced-emoji",
        "rss",
        "sitemap-general",
        "copyright",
        "tbfed-pagefooter",
        "mygitalk",
        "donate",
        "icp",
        "diff",
        "simple-mind-map",
        "hide-element",
        "audio_image",
        "mermaid-gb3",
        "baidu-tongji-with-multiple-channel",
        "google-tongji-with-multiple-channel"
    ],
    "pluginsConfig": {
        "favicon-absolute": {
            "favicon": "/favicon.ico",
            "appleTouchIconPrecomposed152": "/apple-touch-icon-precomposed-152.png"
        },
        "toc": {
            "addClass": true,
            "className": "toc"
        },
        "github-buttons": {
            "buttons": [{
                "user": "snowdreams1006",
                "repo": "snowdreams1006.github.io",
                "type": "star",
                "size": "small"
            }]
        },
        "sharing": {
            "douban": true,
            "facebook": false,
            "google": false,
            "hatenaBookmark": false,
            "instapaper": false,
            "line": false,
            "linkedin": false,
            "messenger": false,
            "pocket": false,
            "qq": true,
            "qzone": true,
            "stumbleupon": false,
            "twitter": false,
            "viber": false,
            "vk": false,
            "weibo": true,
            "whatsapp": false,
            "all": [
                "facebook", "google", "twitter",
                "weibo", "instapaper", "linkedin",
                "pocket", "stumbleupon"
            ]
        },
        "edit-link-plus": {
            "base": {
                "snowdreams1006.github.io": "https://github.com/snowdreams1006/snowdreams1006.github.io/edit/master",
                "snowdreams1006.gitlab.io": "https://gitlab.com/snowdreams1006/snowdreams1006.gitlab.io/edit/master",
                "snowdreams1006.gitee.io": "https://gitee.com/snowdreams1006/snowdreams1006/edit/master"
            },
            "defaultBase": "https://github.com/snowdreams1006/snowdreams1006.github.io/edit/master",
            "label": "编辑本页"
        },
        "chart": {
            "type": "c3"
        },
        "rss": {
            "title": "雪之梦技术驿站",
            "description": "雪之梦技术驿站静态网站,源码托管于 https://github.com/snowdreams1006/snowdreams1006.github.io",
            "author": "snowdreams1006",
            "site_url": "https://snowdreams1006.github.io/",
            "feed_url": "https://snowdreams1006.github.io/rss",
            "managingEditor": "snowdreams1006@163.com",
            "webMaster": "snowdreams1006@163.com",
            "categories": [
                "markdown",
                "git",
                "github",
                "gitbook",
                "java",
                "php"
            ]
        },
        "sitemap-general": {
            "prefix": "https://snowdreams1006.github.io/"
        },
        "copyright": {
            "site": "https://snowdreams1006.github.io/",
            "author": "雪之梦技术驿站",
            "website": "雪之梦技术驿站",
            "image": "https://snowdreams1006.github.io/snowdreams1006-wechat-open.png",
            "copyProtect": false
        },
        "tbfed-pagefooter": {
            "copyright": "&copy snowdreams1006",
            "modify_label": "文件修订时间: ",
            "modify_format": "YYYY-MM-DD HH:mm:ss"
        },
        "mygitalk": {
            "clientID": "3f62415a283d19cbd696",
            "clientSecret": "aed0e1db0620bf5d0e3a3f0225f801997ad74e58",
            "repo": "snowdreams1006.github.io",
            "owner": "snowdreams1006",
            "admin": ["snowdreams1006"],
            "distractionFreeMode": false
        },
        "donate": {
            "wechat": "/wechat.jpg",
            "alipay": "/alipay.jpg",
            "title": "",
            "button": "赏",
            "alipayText": "支付宝",
            "wechatText": "微信"
        },
        "icp": {
            "number": "浙ICP备18042346号"
        },
        "hide-element": {
            "elements": ["a.gitbook-link[href='https://www.gitbook.com']"]
        },
        "simple-mind-map": {
            "preset": "colorful"
        },
        "baidu-tongji-with-multiple-channel": {
            "url": "https://hm.baidu.com/hm.js",
            "multipleChannelConfig": {
                "localhost": {
                    "token": "5273b2f99de3bc190886abb53f62267e"
                },
                "snowdreams1006.tech": {
                    "token": "468a97b20b79bc025d27afbee73d2f39"
                },
                "blog.snowdreams1006.cn": {
                    "token": "606f5db455f771889dcfd16bb2bd313b"
                },
                "snowdreams1006.github.io": {
                    "token": "5273b2f99de3bc190886abb53f62267e"
                },
                "snowdreams1006.gitee.io": {
                    "token": "60ec676f32be4579eb53a430e153f677"
                },
                "snowdreams1006.gitlab.io": {
                    "token": "187a0e5601c4e4987cdb5b8df09c9b21"
                },
                "snowdreams1006.gitbook.io": {
                    "token": "6e2ee1b7bea146b2d6d9382bbf803083"
                }
            }
        },
        "google-tongji-with-multiple-channel": {
            "url": "https://www.googletagmanager.com/gtag/js",
            "multipleChannelConfig": {
                "localhost": {
                    "token": "UA-140787039-2"
                },
                "snowdreams1006.gitbook.io": {
                    "token": "UA-140787039-1"
                },
                "snowdreams1006.github.io": {
                    "token": "UA-140787039-2"
                },
                "snowdreams1006.gitee.io": {
                    "token": "UA-140787039-3"
                },
                "snowdreams1006.gitlab.io": {
                    "token": "UA-140787039-4"
                },
                "snowdreams1006.tech": {
                    "token": "UA-140787039-5"
                },
                "blog.snowdreams1006.cn": {
                    "token": "UA-140787039-6"
                }
            }
        }
    }
}
```
