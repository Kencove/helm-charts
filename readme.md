# HELM Charts

https://typesense.org/docs/guide/migrating-from-algolia.html#step-3-create-a-collection

export TYPESENSE_API_KEY=TYQGYHKyQmnJDe9NFdRjGD2PS2yREa
export TYPESENSE_HOST=review-add-saleor-g4yhvr-search.gc.review-kencove.com
export TYPESENSE_PROTOCOL=https
export TYPESENSE_COLLECTION_NAME=prod.ken-r.USD.products

#  We're parallelize-ing the import using the `parallel` command (make sure you install it first):

parallel --block -5 -a documents.jsonl --tmpdir /tmp --pipepart --cat 'curl -H "X-TYPESENSE-API-KEY: ${TYPESENSE_API_KEY}" -X POST -T {} "${TYPESENSE_PROTOCOL}://${TYPESENSE_HOST}/collections/${TYPESENSE_COLLECTION_NAME}/documents/import?action=upsert"'


curl "https://review-add-saleor-g4yhvr-search.gc.review-kencove.com/collections" \
       -X POST \
       -H "Content-Type: application/json" \
       -H "X-TYPESENSE-API-KEY: ${TYPESENSE_API_KEY}" \
       -d '{
  "name": "prod.ken-r.USD.products",
  "enable_nested_fields": true,
  "fields": [
    {
      "name": "attributes",
      "type": "object",
      "optional": true
    },
    {
      "name": "categories",
      "type": "object",
      "optional": true
    },
    {
      "name": "descriptionPlaintext",
      "type": "string",
      "optional": true
    },
    {
      "name": "grossPrice",
      "type": "float",
      "optional": true
    },
    {
      "name": "inStock",
      "type": "bool",
      "optional": true
    },
    {
      "name": "media",
      "type": "object[]",
      "optional": true
    },
    {
      "name": "metadata",
      "type": "object",
      "optional": true
    },
    {
      "name": "name",
      "type": "string",
      "optional": true
    },
    {
      "name": "objectID",
      "type": "string",
      "optional": true
    },
    {
      "name": "otherVariants",
      "type": "string[]",
      "optional": true
    },
    {
      "name": "pricing",
      "type": "object",
      "optional": true
    },
    {
      "name": "productId",
      "type": "string",
      "optional": true
    },
    {
      "name": "productName",
      "type": "string",
      "optional": true
    },
    {
      "name": "productPricing",
      "type": "object",
      "optional": true
    },
    {
      "name": "sequence",
      "type": "int32",
      "optional": true
    },
    {
      "name": "sku",
      "type": "string",
      "optional": true
    },
    {
      "name": "slug",
      "type": "string",
      "optional": true
    },
    {
      "name": "variantId",
      "type": "string",
      "optional": true
    },
    {
      "name": "variantMetadata",
      "type": "object",
      "optional": true
    },
    {
      "name": "variantName",
      "type": "string",
      "optional": true
    }
  ]
}'
{"created_at":1736141538,"default_sorting_field":"","enable_nested_fields":true,"fields":[{"facet":false,"index":true,"infix":false,"locale":"","name":"attributes","optional":true,"sort":false,"stem":false,"store":true,"type":"object"},{"facet":false,"index":true,"infix":false,"locale":"","name":"categories","optional":true,"sort":false,"stem":false,"store":true,"type":"object"},{"facet":false,"index":true,"infix":false,"locale":"","name":"descriptionPlaintext","optional":true,"sort":false,"stem":false,"store":true,"type":"string"},{"facet":false,"index":true,"infix":false,"locale":"","name":"grossPrice","optional":true,"sort":true,"stem":false,"store":true,"type":"float"},{"facet":false,"index":true,"infix":false,"locale":"","name":"inStock","optional":true,"sort":true,"stem":false,"store":true,"type":"bool"},{"facet":false,"index":true,"infix":false,"locale":"","name":"media","optional":true,"sort":false,"stem":false,"store":true,"type":"object[]"},{"facet":false,"index":true,"infix":false,"locale":"","name":"metadata","optional":true,"sort":false,"stem":false,"store":true,"type":"object"},{"facet":false,"index":true,"infix":false,"locale":"","name":"name","optional":true,"sort":false,"stem":false,"store":true,"type":"string"},{"facet":false,"index":true,"infix":false,"locale":"","name":"objectID","optional":true,"sort":false,"stem":false,"store":true,"type":"string"},{"facet":false,"index":true,"infix":false,"locale":"","name":"otherVariants","optional":true,"sort":false,"stem":false,"store":true,"type":"string[]"},{"facet":false,"index":true,"infix":false,"locale":"","name":"pricing","optional":true,"sort":false,"stem":false,"store":true,"type":"object"},{"facet":false,"index":true,"infix":false,"locale":"","name":"productId","optional":true,"sort":false,"stem":false,"store":true,"type":"string"},{"facet":false,"index":true,"infix":false,"locale":"","name":"productName","optional":true,"sort":false,"stem":false,"store":true,"type":"string"},{"facet":false,"index":true,"infix":false,"locale":"","name":"productPricing","optional":true,"sort":false,"stem":false,"store":true,"type":"object"},{"facet":false,"index":true,"infix":false,"locale":"","name":"sequence","optional":true,"sort":true,"stem":false,"store":true,"type":"int32"},{"facet":false,"index":true,"infix":false,"locale":"","name":"sku","optional":true,"sort":false,"stem":false,"store":true,"type":"string"},{"facet":false,"index":true,"infix":false,"locale":"","name":"slug","optional":true,"sort":false,"stem":false,"store":true,"type":"string"},{"facet":false,"index":true,"infix":false,"locale":"","name":"variantId","optional":true,"sort":false,"stem":false,"store":true,"type":"string"},{"facet":false,"index":true,"infix":false,"locale":"","name":"variantMetadata","optional":true,"sort":false,"stem":false,"store":true,"type":"object"},{"facet":false,"index":true,"infix":false,"locale":"","name":"variantName","optional":true,"sort":false,"stem":false,"store":true,"type":"string"}],"name":"prod.ken-r.USD.products","num_documents":0,"symbols_to_index":[],"token_separators":[]}