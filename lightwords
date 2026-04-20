/*
 *
 *
脚本功能：轻记单词-Lightwords会员解锁
软件版本：1.0.116
下载地址：https://www.babeword.com/
脚本作者：根据需求定制
更新时间：2026-04-20
使用声明：此脚本仅供学习与交流，请在下载使用24小时内删除！请勿用于商业用途！
*******************************
[rewrite_local]
# 用户信息接口 - 解锁VIP
^https?:\/\/www\.babeword\.com\/lw\/seed\/user\/info url script-response-body https://raw.githubusercontent.com/onefan2048/lightword/refs/heads/main/lightwords.js

# 弹窗信息查询 - 移除广告
^https?:\/\/www\.babeword\.com\/lw\/seed\/user\/queryPopInfo url script-response-body https://raw.githubusercontent.com/onefan2048/lightword/refs/heads/main/lightwords-popup.js

# 单词书详情 - 解锁所有内容
^https?:\/\/www\.babeword\.com\/lw\/seed\/word\/book\/unit\/detail\/v2 url script-response-body https://raw.githubusercontent.com/onefan2048/lightword/refs/heads/main/lightwords-content.js

[mitm]
hostname = www.babeword.com
*
*
*/

// 主脚本：lightwords.js - 用户信息VIP解锁
var body = JSON.parse($response.body);

// 检查数据结构，确保兼容性
if (body && body.data) {
    // 用户VIP信息
    body.data.vipInfo = {
        "vipType": 2,                    // VIP类型：2表示高级VIP
        "vipLevel": 3,                   // VIP等级：3最高级
        "isVip": true,                   // 是否是VIP
        "vipExpireTime": "9999-12-31 23:59:59", // VIP过期时间
        "vipStartTime": "2026-01-01 00:00:00",  // VIP开始时间
        "vipDays": 99999,                // VIP天数
        "remainDays": 99999,             // 剩余天数
        "isPermanent": true,             // 是否永久VIP
        "productId": "lightwords.super.vip", // 产品ID
        "price": 298,                    // 价格
        "originalPrice": 998,            // 原价
        "discount": 70                   // 折扣
    };
    
    // 用户权限信息
    body.data.userRole = {
        "roleId": 3,                     // 角色ID：3为超级用户
        "roleName": "超级会员",
        "permissions": [
            "unlock_all_content",        // 解锁所有内容
            "no_ads",                    // 无广告
            "unlimited_practice",        // 无限练习
            "download_offline",          // 离线下载
            "custom_learning_plan",      // 自定义学习计划
            "ai_assistant"               // AI助手
        ],
        "valid": true
    };
    
    // 用户账户状态
    body.data.accountStatus = {
        "status": "active",
        "premium": true,
        "trialUsed": false,
        "subscriptionType": "lifetime",
        "nextBillingDate": null,
        "autoRenew": false
    };
    
    // 学习统计（增强版）
    body.data.learningStats = {
        "totalWordsLearned": 9999,
        "currentStreak": 365,
        "longestStreak": 365,
        "totalLearningTime": 8760,       // 小时
        "accuracyRate": 98.5,
        "reviewCount": 99999,
        "achievements": 50
    };
    
    // 解锁的功能列表
    body.data.unlockedFeatures = {
        "allWordBooks": true,            // 所有单词书
        "allCourses": true,              // 所有课程
        "aiPronunciation": true,         // AI发音评测
        "offlineMode": true,             // 离线模式
        "customTests": true,             // 自定义测试
        "progressAnalytics": true,       // 进度分析
        "exportData": true,              // 数据导出
        "prioritySupport": true          // 优先支持
    };
    
    // 资源配额（无限）
    body.data.resourceQuotas = {
        "dailyWordLimit": 9999,
        "monthlyReviewLimit": 99999,
        "offlineDownloadLimit": 9999,
        "aiPracticeLimit": 9999,
        "exportLimit": 9999,
        "storageQuota": 10737418240      // 10GB存储
    };
    
    // 会员等级标识
    body.data.memberLevel = "platinum";
    body.data.isPremiumMember = true;
    body.data.memberSince = "2026-01-01";
}

$done({ body: JSON.stringify(body) });
