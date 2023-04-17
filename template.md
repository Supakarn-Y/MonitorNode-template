{
  "annotations": {
    "list": [
      {
        "builtIn": 1,
        "datasource": {
          "type": "datasource",
          "uid": "grafana"
        },
        "enable": true,
        "hide": true,
        "iconColor": "rgba(0, 211, 255, 1)",
        "name": "Annotations & Alerts",
        "target": {
          "limit": 100,
          "matchAny": false,
          "tags": [],
          "type": "dashboard"
        },
        "type": "dashboard"
      }
    ]
  },
  "description": "Kubernetes Nodes for node exporter 0.16+ (via Prometheus)\r\n",
  "editable": true,
  "fiscalYearStartMonth": 0,
  "gnetId": 8171,
  "graphTooltip": 0,
  "id": 2,
  "links": [],
  "liveNow": false,
  "panels": [
    {
      "collapsed": false,
      "gridPos": {
        "h": 1,
        "w": 24,
        "x": 0,
        "y": 0
      },
      "id": 22,
      "panels": [],
      "title": "Kubernetes SCSU Prod",
      "type": "row"
    },
    {
      "aliasColors": {},
      "bars": false,
      "dashLength": 10,
      "dashes": false,
      "datasource": {
        "type": "prometheus",
        "uid": "ndc61OP4z"
      },
      "editable": true,
      "error": false,
      "fill": 1,
      "fillGradient": 0,
      "grid": {
        "threshold1Color": "rgba(216, 200, 27, 0.27)",
        "threshold2Color": "rgba(234, 112, 112, 0.22)"
      },
      "gridPos": {
        "h": 8,
        "w": 12,
        "x": 0,
        "y": 1
      },
      "hiddenSeries": false,
      "id": 48,
      "isNew": false,
      "legend": {
        "alignAsTable": false,
        "avg": false,
        "current": false,
        "hideEmpty": false,
        "hideZero": false,
        "max": false,
        "min": false,
        "rightSide": false,
        "show": true,
        "total": false,
        "values": false
      },
      "lines": true,
      "linewidth": 2,
      "links": [],
      "nullPointMode": "connected",
      "options": {
        "alertThreshold": true
      },
      "percentage": false,
      "pluginVersion": "9.4.7",
      "pointradius": 5,
      "points": false,
      "renderer": "flot",
      "seriesOverrides": [],
      "spaceLength": 10,
      "stack": false,
      "steppedLine": false,
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "ndc61OP4z"
          },
          "editorMode": "code",
          "expr": "100 - (avg(irate(node_cpu_seconds_total{mode=\"idle\",instance=\"10.0.8.2:9100\"}[1m])) * 100) ",
          "format": "time_series",
          "hide": false,
          "intervalFactor": 10,
          "legendFormat": "10.148.8.38",
          "range": true,
          "refId": "A",
          "step": 50
        }
      ],
      "thresholds": [],
      "timeRegions": [],
      "title": "Idle CPU",
      "tooltip": {
        "msResolution": false,
        "shared": true,
        "sort": 0,
        "value_type": "cumulative"
      },
      "type": "graph",
      "xaxis": {
        "mode": "time",
        "show": true,
        "values": []
      },
      "yaxes": [
        {
          "$$hashKey": "object:592",
          "format": "percent",
          "label": "cpu usage",
          "logBase": 1,
          "max": 100,
          "min": 0,
          "show": true
        },
        {
          "$$hashKey": "object:593",
          "format": "short",
          "logBase": 1,
          "show": true
        }
      ],
      "yaxis": {
        "align": false
      }
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "ndc61OP4z"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 10,
            "gradientMode": "none",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "lineInterpolation": "linear",
            "lineStyle": {
              "fill": "solid"
            },
            "lineWidth": 2,
            "pointSize": 5,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "never",
            "spanNulls": true,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "mappings": [],
          "max": 33000000000,
          "min": 0,
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 80
              }
            ]
          },
          "unit": "bytes"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 8,
        "w": 12,
        "x": 12,
        "y": 1
      },
      "id": 61,
      "links": [],
      "options": {
        "legend": {
          "calcs": [],
          "displayMode": "list",
          "placement": "bottom",
          "showLegend": true
        },
        "timezones": [
          "Asia/Bangkok"
        ],
        "tooltip": {
          "mode": "multi",
          "sort": "none"
        }
      },
      "pluginVersion": "9.1.0",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "ndc61OP4z"
          },
          "editorMode": "code",
          "expr": "node_memory_MemTotal_bytes{instance=\"10.0.8.2:9100\"} - node_memory_MemFree_bytes{instance=\"10.0.8.2:9100\"} - node_memory_Buffers_bytes{instance=\"10.0.8.2:9100\"} - node_memory_Cached_bytes{instance=\"10.0.8.2:9100\"}",
          "format": "time_series",
          "hide": false,
          "interval": "",
          "intervalFactor": 1,
          "legendFormat": "10.148.8.38",
          "metric": "",
          "range": true,
          "refId": "C",
          "step": 10
        }
      ],
      "title": "Memory Usage",
      "type": "timeseries"
    },
    {
      "datasource": {
        "type": "prometheus",
        "uid": "ndc61OP4z"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "palette-classic"
          },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 8,
            "gradientMode": "none",
            "hideFrom": {
              "legend": false,
              "tooltip": false,
              "viz": false
            },
            "lineInterpolation": "linear",
            "lineStyle": {
              "fill": "solid"
            },
            "lineWidth": 2,
            "pointSize": 1,
            "scaleDistribution": {
              "type": "linear"
            },
            "showPoints": "never",
            "spanNulls": false,
            "stacking": {
              "group": "A",
              "mode": "none"
            },
            "thresholdsStyle": {
              "mode": "off"
            }
          },
          "mappings": [
            {
              "options": {
                "match": "null",
                "result": {
                  "text": "N/A"
                }
              },
              "type": "special"
            }
          ],
          "max": 1,
          "min": 0,
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "rgba(50, 172, 45, 0.97)",
                "value": null
              },
              {
                "color": "rgba(237, 129, 40, 0.89)",
                "value": 0.75
              },
              {
                "color": "rgba(245, 54, 54, 0.9)",
                "value": 0.9
              }
            ]
          },
          "unit": "percentunit"
        },
        "overrides": []
      },
      "gridPos": {
        "h": 8,
        "w": 8,
        "x": 0,
        "y": 9
      },
      "hideTimeOverride": false,
      "id": 54,
      "links": [],
      "maxDataPoints": 100,
      "options": {
        "legend": {
          "calcs": [],
          "displayMode": "list",
          "placement": "bottom",
          "showLegend": true
        },
        "tooltip": {
          "mode": "single",
          "sort": "none"
        }
      },
      "pluginVersion": "9.1.0",
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "ndc61OP4z"
          },
          "editorMode": "code",
          "expr": "(sum(node_filesystem_size_bytes{device!=\"rootfs\",instance=\"10.0.8.2:9100\"}) - sum(node_filesystem_free_bytes{device!=\"rootfs\",instance=\"10.0.8.2:9100\"})) / sum(node_filesystem_size_bytes{device!=\"rootfs\",instance=\"10.0.8.2:9100\"})",
          "format": "time_series",
          "intervalFactor": 2,
          "legendFormat": "10.148.8.38",
          "range": true,
          "refId": "A",
          "step": 60,
          "target": ""
        }
      ],
      "title": "Disk Space Usage",
      "type": "timeseries"
    },
    {
      "aliasColors": {},
      "bars": false,
      "dashLength": 10,
      "dashes": false,
      "datasource": {
        "type": "prometheus",
        "uid": "ndc61OP4z"
      },
      "editable": true,
      "error": false,
      "fill": 1,
      "fillGradient": 0,
      "grid": {
        "threshold1Color": "rgba(216, 200, 27, 0.27)",
        "threshold2Color": "rgba(234, 112, 112, 0.22)"
      },
      "gridPos": {
        "h": 8,
        "w": 8,
        "x": 8,
        "y": 9
      },
      "hiddenSeries": false,
      "id": 50,
      "isNew": false,
      "legend": {
        "alignAsTable": false,
        "avg": false,
        "current": false,
        "hideEmpty": false,
        "hideZero": false,
        "max": false,
        "min": false,
        "rightSide": false,
        "show": true,
        "total": false,
        "values": false
      },
      "lines": true,
      "linewidth": 2,
      "links": [],
      "nullPointMode": "connected",
      "options": {
        "alertThreshold": true
      },
      "percentage": false,
      "pluginVersion": "9.4.7",
      "pointradius": 5,
      "points": false,
      "renderer": "flot",
      "seriesOverrides": [],
      "spaceLength": 10,
      "stack": false,
      "steppedLine": false,
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "ndc61OP4z"
          },
          "editorMode": "code",
          "expr": "node_load1{instance=\"10.0.8.2:9100\"}/100",
          "intervalFactor": 1,
          "legendFormat": "10.148.8.38",
          "range": true,
          "refId": "A",
          "step": 20,
          "target": ""
        }
      ],
      "thresholds": [],
      "timeRegions": [],
      "title": "System Load",
      "tooltip": {
        "msResolution": false,
        "shared": true,
        "sort": 0,
        "value_type": "cumulative"
      },
      "type": "graph",
      "xaxis": {
        "mode": "time",
        "show": true,
        "values": []
      },
      "yaxes": [
        {
          "format": "percentunit",
          "logBase": 1,
          "show": true
        },
        {
          "format": "short",
          "logBase": 1,
          "show": true
        }
      ],
      "yaxis": {
        "align": false
      }
    },
    {
      "aliasColors": {},
      "bars": false,
      "dashLength": 10,
      "dashes": false,
      "datasource": {
        "type": "prometheus",
        "uid": "ndc61OP4z"
      },
      "editable": true,
      "error": false,
      "fill": 1,
      "fillGradient": 0,
      "grid": {
        "threshold1Color": "rgba(216, 200, 27, 0.27)",
        "threshold2Color": "rgba(234, 112, 112, 0.22)"
      },
      "gridPos": {
        "h": 8,
        "w": 8,
        "x": 16,
        "y": 9
      },
      "hiddenSeries": false,
      "id": 46,
      "isNew": true,
      "legend": {
        "alignAsTable": false,
        "avg": false,
        "current": false,
        "hideEmpty": false,
        "hideZero": false,
        "max": false,
        "min": false,
        "rightSide": false,
        "show": true,
        "total": false,
        "values": false
      },
      "lines": true,
      "linewidth": 2,
      "links": [],
      "nullPointMode": "connected",
      "options": {
        "alertThreshold": true
      },
      "percentage": false,
      "pluginVersion": "9.4.7",
      "pointradius": 5,
      "points": false,
      "renderer": "flot",
      "seriesOverrides": [
        {
          "$$hashKey": "object:354",
          "alias": "read",
          "yaxis": 1
        },
        {
          "$$hashKey": "object:355",
          "alias": "{instance=\"172.17.0.1:9100\"}",
          "yaxis": 2
        },
        {
          "$$hashKey": "object:356",
          "alias": "io time",
          "yaxis": 2
        }
      ],
      "spaceLength": 10,
      "stack": false,
      "steppedLine": false,
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "ndc61OP4z"
          },
          "editorMode": "code",
          "expr": "sum by (instance) (rate(node_disk_io_time_seconds_total{instance=\"10.0.8.2:9100\"}[1m]))",
          "format": "time_series",
          "hide": false,
          "intervalFactor": 4,
          "legendFormat": "10.148.8.38",
          "range": true,
          "refId": "C",
          "step": 20
        }
      ],
      "thresholds": [],
      "timeRegions": [],
      "title": "Disk I/O",
      "tooltip": {
        "msResolution": false,
        "shared": true,
        "sort": 0,
        "value_type": "cumulative"
      },
      "type": "graph",
      "xaxis": {
        "mode": "time",
        "show": true,
        "values": []
      },
      "yaxes": [
        {
          "format": "bytes",
          "logBase": 1,
          "show": true
        },
        {
          "format": "ms",
          "logBase": 1,
          "show": true
        }
      ],
      "yaxis": {
        "align": false
      }
    },
    {
      "aliasColors": {},
      "bars": false,
      "dashLength": 10,
      "dashes": false,
      "datasource": {
        "type": "prometheus",
        "uid": "ndc61OP4z"
      },
      "editable": true,
      "error": false,
      "fill": 1,
      "fillGradient": 0,
      "grid": {
        "threshold1Color": "rgba(216, 200, 27, 0.27)",
        "threshold2Color": "rgba(234, 112, 112, 0.22)"
      },
      "gridPos": {
        "h": 8,
        "w": 12,
        "x": 0,
        "y": 17
      },
      "hiddenSeries": false,
      "id": 56,
      "isNew": false,
      "legend": {
        "alignAsTable": false,
        "avg": false,
        "current": false,
        "hideEmpty": false,
        "hideZero": false,
        "max": false,
        "min": false,
        "rightSide": false,
        "show": true,
        "total": false,
        "values": false
      },
      "lines": true,
      "linewidth": 2,
      "links": [],
      "nullPointMode": "connected",
      "options": {
        "alertThreshold": true
      },
      "percentage": false,
      "pluginVersion": "9.4.7",
      "pointradius": 5,
      "points": false,
      "renderer": "flot",
      "seriesOverrides": [
        {
          "$$hashKey": "object:429",
          "alias": "transmitted",
          "yaxis": 2
        }
      ],
      "spaceLength": 10,
      "stack": false,
      "steppedLine": false,
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "ndc61OP4z"
          },
          "editorMode": "code",
          "expr": "rate(node_network_receive_bytes_total{instance=\"10.0.8.2:9100\",device=\"eth0\"}[1m])",
          "format": "time_series",
          "hide": false,
          "intervalFactor": 2,
          "legendFormat": "10.148.8.38",
          "range": true,
          "refId": "A",
          "step": 10,
          "target": ""
        }
      ],
      "thresholds": [],
      "timeRegions": [],
      "title": "Network Received",
      "tooltip": {
        "msResolution": false,
        "shared": true,
        "sort": 0,
        "value_type": "cumulative"
      },
      "type": "graph",
      "xaxis": {
        "mode": "time",
        "show": true,
        "values": []
      },
      "yaxes": [
        {
          "format": "bytes",
          "logBase": 1,
          "show": true
        },
        {
          "format": "bytes",
          "logBase": 1,
          "show": true
        }
      ],
      "yaxis": {
        "align": false
      }
    },
    {
      "aliasColors": {},
      "bars": false,
      "dashLength": 10,
      "dashes": false,
      "datasource": {
        "type": "prometheus",
        "uid": "ndc61OP4z"
      },
      "editable": true,
      "error": false,
      "fill": 1,
      "fillGradient": 0,
      "grid": {
        "threshold1Color": "rgba(216, 200, 27, 0.27)",
        "threshold2Color": "rgba(234, 112, 112, 0.22)"
      },
      "gridPos": {
        "h": 8,
        "w": 12,
        "x": 12,
        "y": 17
      },
      "hiddenSeries": false,
      "id": 57,
      "isNew": false,
      "legend": {
        "alignAsTable": false,
        "avg": false,
        "current": false,
        "hideEmpty": false,
        "hideZero": false,
        "max": false,
        "min": false,
        "rightSide": false,
        "show": true,
        "total": false,
        "values": false
      },
      "lines": true,
      "linewidth": 2,
      "links": [],
      "nullPointMode": "connected",
      "options": {
        "alertThreshold": true
      },
      "percentage": false,
      "pluginVersion": "9.4.7",
      "pointradius": 5,
      "points": false,
      "renderer": "flot",
      "seriesOverrides": [
        {
          "$$hashKey": "object:490",
          "alias": "transmitted",
          "yaxis": 2
        }
      ],
      "spaceLength": 10,
      "stack": false,
      "steppedLine": false,
      "targets": [
        {
          "datasource": {
            "type": "prometheus",
            "uid": "ndc61OP4z"
          },
          "editorMode": "code",
          "expr": "rate(node_network_transmit_bytes_total{instance=\"10.0.8.2:9100\",device=\"eth0\"}[1m])",
          "format": "time_series",
          "hide": false,
          "intervalFactor": 2,
          "legendFormat": "10.148.8.38",
          "range": true,
          "refId": "B",
          "step": 10,
          "target": ""
        }
      ],
      "thresholds": [],
      "timeRegions": [],
      "title": "Network Transmitted",
      "tooltip": {
        "msResolution": false,
        "shared": true,
        "sort": 0,
        "value_type": "cumulative"
      },
      "type": "graph",
      "xaxis": {
        "mode": "time",
        "show": true,
        "values": []
      },
      "yaxes": [
        {
          "format": "bytes",
          "logBase": 1,
          "show": true
        },
        {
          "format": "bytes",
          "logBase": 1,
          "show": true
        }
      ],
      "yaxis": {
        "align": false
      }
    }
  ],
  "refresh": "",
  "revision": 1,
  "schemaVersion": 38,
  "style": "dark",
  "tags": [
    "nodes",
    "prometheus"
  ],
  "templating": {
    "list": []
  },
  "time": {
    "from": "now-1h",
    "to": "now"
  },
  "timepicker": {
    "refresh_intervals": [
      "5s",
      "10s",
      "30s",
      "1m",
      "5m",
      "15m",
      "30m",
      "1h",
      "2h",
      "1d"
    ],
    "time_options": [
      "5m",
      "15m",
      "1h",
      "6h",
      "12h",
      "24h",
      "2d",
      "7d",
      "30d"
    ]
  },
  "timezone": "Asia/Bangkok",
  "title": "Kubernetes Monitoring Cluster",
  "uid": "dUMN5x0mk2",
  "version": 7,
  "weekStart": ""
}
