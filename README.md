# amazon-mws (Amazon Marketplace Web Service)

This API supported Amazon Marketplace Web Service(MWS)'s standard REST-style API that accepts/returns JSON requests and Here is the [API reference] (http://docs.developer.amazonservices.com/en_IN/dev_guide/DG_IfNew.html)

You can find [examples here](https://github.com/bhushankumarl/amazon-mws/tree/master/examples). This will help you for faster implmentation of Amazon Marketplace Web Service's(MWS).

##### It supports pure JSON response.
##### All methods support Promise and Callback

## Installation
```bash
$ npm install amazon-mws --save
```

## Debugging

Run the DEBUG:

```bash
$ export DEBUG=MWS:*
```

## Development

Run the installation:

```bash
$ npm install
```


## Configuration

Set your Access Key and Access Secret.

```js
var amazonMws = require('amazon-mws')('AWS_ACCESS_KEY_ID','AWS_SECRET_ACCESS_KEY');
```

### Feeds

#### Get Feed Submission List
```js
    amazonMws.feeds.search({
        'Version': '2009-01-01',
        'Action': 'GetFeedSubmissionList',
        'SellerId': 'SELLER_ID',
        'MWSAuthToken': 'MWS_AUTH_TOKEN'
    }, function (error, response) {
        if (error) {
            console.log('error ', error);
            return;
        }
        console.log('response', response);
    });
```

### Finances

#### List Financial Event Groups
```js
    amazonMws.finances.search({
        'Version': '2015-05-01',
        'Action': 'ListFinancialEventGroups',
        'SellerId': 'SELLER_ID',
        'MWSAuthToken': 'MWS_AUTH_TOKEN',
        'FinancialEventGroupStartedAfter': new Date(13, 12, 2016)
    }, function (error, response) {
        if (error) {
            console.log('error ', error);
            return;
        }
        console.log('response', response);
    });
```

### FulfillmentInboundShipment

#### Get Inbound Guidance For SKU
```js
    amazonMws.fulfillmentInboundShipment.search({
        'Version': '2010-10-01',
        'Action': 'GetInboundGuidanceForSKU',
        'SellerId': 'SELLER_ID',
        'MWSAuthToken': 'MWS_AUTH_TOKEN',
        'MarketplaceId': 'MARKET_PLACE_ID',
        'SellerSKUList.Id.1': 'us001'
    }, function (error, response) {
        if (error) {
            console.log('error ', error);
            return;
        }
        console.log('response', response);
    });
```

### FulfillmentInventory

#### List Inventory Supply
```js
    amazonMws.fulfillmentInventory.search({
        'Version': '2010-10-01',
        'Action': 'ListInventorySupply',
        'SellerId': 'SELLER_ID',
        'MWSAuthToken': 'MWS_AUTH_TOKEN',
        'MarketplaceId': 'MARKET_PLACE_ID',
        'QueryStartDateTime': new Date(13, 12, 2016)
    }, function (error, response) {
        if (error) {
            console.log('error ', error);
            return;
        }
        console.log('response', response);
    });
```

### Orders

#### List Orders
```js
    amazonMws.orders.search({
        'Version': '2013-09-01',
        'Action': 'ListOrders',
        'SellerId': 'SELLER_ID',
        'MWSAuthToken': 'MWS_AUTH_TOKEN',
        'MarketplaceId.Id.1': 'MARKET_PLEACE_ID_1',
        'LastUpdatedAfter': new Date(13, 12, 2016)
    }, function (error, response) {
        if (error) {
            console.log('error ', error);
            return;
        }
        console.log('response', response);
    });
```

### Products

#### List Matching Products
```js
    amazonMws.products.search({
        'Version': '2011-10-01',
        'Action': 'ListMatchingProducts',
        'SellerId': 'SELLER_ID',
        'MWSAuthToken': 'MWS_AUTH_TOKEN',
        'MarketplaceId': 'MARKET_PLACE_ID',
        'Query':'k'
    }, function (error, response) {
        if (error) {
            console.log('error ', error);
            return;
        }
        console.log('response', response);
    });
```

#### List Matching Products Using Promise
```js
    amazonMws.products.search({
        'Version': '2011-10-01',
        'Action': 'GetMatchingProduct',
        'SellerId': 'SELLER_ID',
        'MWSAuthToken': 'MWS_AUTH_TOKEN',
        'MarketplaceId': 'MARKET_PLACE_ID',
        'ASINList.ASIN.1': 'ASIN_1'
    }).then(function (response) {
        console.log('response', response);
    }).catch(function (error) {
        console.log('error products', error);
    });
```

### Sellers

#### List Marketplace Participations
```js
    amazonMws.sellers.search({
        'Version': '2011-07-01',
        'Action': 'ListMarketplaceParticipations',
        'SellerId': 'SELLER_ID',
        'MWSAuthToken': 'MWS_AUTH_TOKEN'
    }, function (error, response) {
        if (error) {
            console.log('error ', error);
            return;
        }
        console.log('response', response);
        // asynchronously called
    });
```

#### List Marketplace Participations By Next Token
```js
    amazonMws.sellers.search({
        'Version': '2011-07-01',
        'Action': 'ListMarketplaceParticipationsByNextToken',
        'SellerId': 'SELLER_ID',
        'MWSAuthToken': 'MWS_AUTH_TOKEN',
        'NextToken': 'NEXT_TOKEN'
    }, function (error, response) {
        if (error) {
            console.log('error ', error);
            return;
        }
        console.log('response', response);
        // asynchronously called
    });
```

### Reports

#### Get Report List
```js
    amazonMws.reports.search({
        'Version': '2009-01-01',
        'Action': 'GetReportList',
        'SellerId': 'SELLER_ID',
        'MWSAuthToken': 'MWS_AUTH_TOKEN',
        'ReportTypeList.Type.1': 'REPORT_TYPE_LIST'
    }, function (error, response) {
        if (error) {
            console.log('error ', error);
            return;
        }
        console.log('response', response);
    });
```

#### Get Report
```js
    amazonMws.reports.search({
        'Version': '2009-01-01',
        'Action': 'GetReport',
        'SellerId': 'SELLER_ID',
        'MWSAuthToken': 'MWS_AUTH_TOKEN',
        'ReportId':'REPORT_ID'
    }, function (error, response) {
        if (error) {
            console.log('error ', error);
            return;
        }
        console.log('response', response);
    });
```
Originally by [Bhushankumar Lilapara](https://github.com/bhushankumarl) (bhushankumar.lilapara@gmail.com).

