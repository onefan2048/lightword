// lightwords-content.js - 解锁所有学习内容
var body = JSON.parse($response.body);

if (body && body.data) {
    // 解锁所有单元
    if (body.data.units) {
        body.data.units.forEach(unit => {
            unit.locked = false;
            unit.accessible = true;
            unit.previewOnly = false;
            unit.requiresPurchase = false;
        });
    }
    
    // 解锁所有单词
    if (body.data.words) {
        body.data.words.forEach(word => {
            word.locked = false;
            word.premiumOnly = false;
            word.requiresUnlock = false;
        });
    }
    
    // 解锁所有练习
    if (body.data.exercises) {
        body.data.exercises.forEach(exercise => {
            exercise.available = true;
            exercise.restricted = false;
            exercise.limitReached = false;
        });
    }
    
    // 设置VIP访问权限
    body.data.accessControl = {
        "hasAccess": true,
        "accessLevel": "full",
        "restrictions": [],
        "limitations": {}
    };
}

$done({ body: JSON.stringify(body) });
