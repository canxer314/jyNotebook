前台利用ajax进行传送数据

```

$(function () {
    $('#submit-btn').click(function (event) {
        event.preventDefault();

        var telephone_input = $('input[name="telephone"]');
        var sms_captcha_input = $('input[name="sms_captcha"]');
        var username_input = $('input[name="username"]');
        var password1_input = $('input[name="password1"]');
        var password2_input = $('input[name="password2"]');
        var graph_captcha_input = $('input[name="graph_captcha"]');

        var telephone = telephone_input.val();
        var sms_captcha = sms_captcha_input.val();
        var username = username_input.val();
        var password1 = password1_input.val();
        var password2 = password2_input.val();
        var graph_captcha = graph_captcha_input.val();

        zlajax.post({
            "url":"/signup/",
            'data':{
                'telephone':telephone,
                'sms_captcha':sms_captcha,
                'username':username,
                'password1':password1,
                'password2':password2,
                'graph_captcha':graph_captcha,
            },
            'success':function (data) {
                if (data["code"] == 200){
                    //跳转到首页
                    window.location = '/';
                } else{
                  zlalert.alertInfo(data["message"]);
                }
            },
            'fail':function () {
                zlalert.alertNetworkError();
            },
        });
    });
});
```



