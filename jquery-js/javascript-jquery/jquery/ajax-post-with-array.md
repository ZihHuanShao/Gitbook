# ajax post with array

```javascript

var param = {
    "serialno": ["1111-1111-1111-1111","2222-2222-2222-2222"]
};

verify_serialno_before_confirm: function (param, callback) {
    var ajax_options = {
        type: "POST",
        url: "../latr/licmgr/verify_serialno_before_confirm",
        traditional: true, // !!!!!!
        cache: false,
        data: param,
        success: function (data, textStatus, jqXHR) {
            console.log("licmgr/verify_serialno_before_confirm: ", data);

            switch (data.code) {
                case '500':
                    showErrorAlert(Utils.i18n("admin.contactformview.error_system", "系統發生錯誤"));
                    break;
                case '200':
                    break;
                default:
                    break;
            }
            callback(data.code);
        },
        error: function(jqXHR, textStatus, errorThrown) {
            showErrorAlert("Server Error, textStatus:" + textStatus);
        }
    };
    $.ajax(ajax_options);
}
```

