# GoogleMap Api: Geocoding

**目的是希望透過輸入任意地址或地名，能夠獲得相對應的經緯度**，並再透過經緯資訊將畫面導到該位址上。

### Request

API example`https://maps.googleapis.com/maps/api/geocode/json?address=台中美術館&key=API_KEY`

`台中美術館`可以換成其他想查詢的地址

`API_KEY`：填入在[google api 官網](https://cloud.google.com/maps-platform/?utm_source=google&utm_medium=cpc&utm_campaign=FY18-Q2-global-demandgen-paidsearchonnetworkhouseads-cs-maps_contactsal_saf&utm_content=text-ad-none-none-DEV_c-CRE_396517150297-ADGP_Hybrid%20%7C%20AW%20SEM%20%7C%20SKWS%20~%20Maps%20%7C%20BMM%20%7C%20Mapping%20APIs-KWID_43700049560642562-kwd-297933066873-userloc_9040380&utm_term=KW_%2Bmaps%20%2Bapi-ST_%2Bmaps%20%2Bapi&gclid=CjwKCAiAv4n9BRA9EiwA30WND6Za4rWKE9efwQV6sBI36aCwpYwfynT_2lC2GlGePYRnLc0gwKbi0xoCxJsQAvD_BwE)申請Geocoding API的Key。現在申請必須要給信用卡帳戶資料了，不過還是有免費額度可以使用（[收費制度](https://cloud.google.com/maps-platform/pricing)），要呼叫1000次才會收費5塊美金，不過google額外還會提供每個月200塊美金，所以若非商業用，也很難會需要付費。

若上述步驟都已完成，可將上面網址直接貼到瀏覽器看傳送結果。

### Debug

當回傳**`INVALID_REQUEST`**時，可以將要request的字串 \(如`https://maps.googleapis.com/maps/api/geocode/json?address=台中美術館&key=API_KEY`\)，直接貼在瀏覽器的網址列上執行看看，會告訴我們錯誤的因素。

### Response

```javascript
{
   "results" : [
      {
         "address_components" : [
            {
               "long_name" : "2號",
               "short_name" : "2號",
               "types" : [ "street_number" ]
            },
            {
               "long_name" : "五權西路一段",
               "short_name" : "五權西路一段",
               "types" : [ "route" ]
            },
            {
               "long_name" : "西區",
               "short_name" : "西區",
               "types" : [ "administrative_area_level_3", "political" ]
            },
            {
               "long_name" : "台中市",
               "short_name" : "台中市",
               "types" : [ "administrative_area_level_1", "political" ]
            },
            {
               "long_name" : "台灣",
               "short_name" : "TW",
               "types" : [ "country", "political" ]
            },
            {
               "long_name" : "403",
               "short_name" : "403",
               "types" : [ "postal_code" ]
            }
         ],
         "formatted_address" : "403台灣台中市西區五權西路一段2號",
         "geometry" : {
            "location" : {
               "lat" : 24.141216,
               "lng" : 120.6626202
            },
            "location_type" : "ROOFTOP",
            "viewport" : {
               "northeast" : {
                  "lat" : 24.14256498029151,
                  "lng" : 120.6639691802915
               },
               "southwest" : {
                  "lat" : 24.1398670197085,
                  "lng" : 120.6612712197085
               }
            }
         },
         "place_id" : "ChIJyVHkNqY9aTQRDilsyqDVfbg",
         "plus_code" : {
            "compound_code" : "4MR7+F2 台灣台中市西區",
            "global_code" : "7QP24MR7+F2"
         },
         "types" : [ "establishment", "museum", "point_of_interest" ]
      }
   ],
   "status" : "OK"
}
```

`geometry`中的`location`是我們要取得的，也就是台中美術館的座標

## Ref.

{% embed url="https://developers.google.com/maps/documentation/geocoding/get-api-key" %}

{% embed url="https://developers.google.com/maps/documentation/geocoding/overview" %}

{% embed url="https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E6%95%99%E5%AE%A4/google-map-%E7%B6%93%E7%B7%AF%E5%BA%A6%E8%BD%89%E6%8F%9B%E5%9C%B0%E5%9D%80-15fba940266f" %}



