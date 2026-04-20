// lightwords-popup.js - 移除广告弹窗
var body = JSON.parse($response.body);

if (body && body.data) {
    // 清空所有广告和弹窗信息
    body.data.popups = [];
    body.data.ads = [];
    body.data.promotions = [];
    body.data.notifications = [];
    
    // 设置无广告状态
    body.data.adConfig = {
        "showAds": false,
        "adFrequency": 0,
        "adTypes": [],
        "adEnabled": false
    };
    
    // 设置VIP专属状态
    body.data.vipBenefits = {
        "adFree": true,
        "noInterruptions": true,
        "priorityContent": true
    };
}

$done({ body: JSON.stringify(body) });
