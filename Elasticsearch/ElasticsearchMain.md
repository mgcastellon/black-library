## Main useful queries

GET _cat/nodes

GET _cluster/health

GET _cat/indices?v

GET _cluster/pending_tasks

GET _cat/shards

PUT _all/_settings
{ 
  "index": 
  { "blocks.read_only" : null
  } 
}

PUT _settings
    {
    "index": {
    "blocks": {
    "read_only_allow_delete": "false"
    }
    }
    } 
