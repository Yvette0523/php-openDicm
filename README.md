# php-openDicm

<?php
// 設定 API 端點 URL 和 API 密鑰
$apiUrl = 'http://your-opendcim-url/api/endpoint';
$apiKey = 'your-api-key';  // 用您自己的 API 密鑰

// 設定 cURL 選項
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, $apiUrl);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, C URLOPT_HTTPHEADER, array(
    'Authorization: Bearer ' . $apiKey,  // 設定 API key
    'Content-Type: application/json'      // 設定內容類型
));

// 執行 API 請求並取得回應
$response = curl_exec($ch);

// 檢查是否有錯誤
if(curl_errno($ch)) {
    echo 'Curl error: ' . curl_error($ch);
} else {
    // 輸出 API 回應
    echo 'Response from OpenDCIM: ' . $response;
}

// 關閉 cURL 資源
curl_close($ch);
?>
