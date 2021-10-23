Provides URL scanning and rewriting of inbound email messages in mail flow, and time-of-click verification of URLs and links in email messages and other locations.
This integration was integrated and tested with version xx of O365 Defender SafeLinks

## Configure O365 Defender SafeLinks on Cortex XSOAR

1. Navigate to **Settings** > **Integrations** > **Servers & Services**.
2. Search for O365 Defender SafeLinks.
3. Click **Add instance** to create and configure a new integration instance.

    | **Parameter** | **Description** | **Required** |
    | --- | --- | --- |
    | Certificate | A pfx certificate encoded in Base64. | True |
    | Password - Used to generate to certificate |  | True |
    | Organization | The organization used in app-only authentication. | True |
    | The application ID from the Azure portal |  | True |

4. Click **Test** to validate the URLs, token, and connection.
## Commands
You can execute these commands from the Cortex XSOAR CLI, as part of an automation, or in a playbook.
After you successfully execute a command, a DBot message appears in the War Room with the command details.
### o365-defender-safelinks-policy-list
***
List Safe Links policies in your cloud-based organization.


#### Base Command

`o365-defender-safelinks-policy-list`
#### Input

| **Argument Name** | **Description** | **Required** |
| --- | --- | --- |
| identity | The Identity of the Safe Links policy that you want to view. Available identity fields of the policy are: Name, Distinguished name (DN), GUID. | Optional | 


#### Context Output

| **Path** | **Type** | **Description** |
| --- | --- | --- |
| O365Defender.SafeLinks.AdminDisplayName | String | Policy description. | 
| O365Defender.SafeLinks.Policy.AllowClickThrough | Boolean | Whether users are allowed to clicl through the original URL. | 
| O365Defender.SafeLinks.Policy.CustomNotificationText | String | The customized notification text to show to users. | 
| O365Defender.SafeLinks.Policy.DeliverMessageAfterScan | Boolean | Whether the mail is delivered after Safe Links scanning was complete or not. | 
| O365Defender.SafeLinks.Policy.DisableUrlRewrite | Boolean | Whether URLs are rewriten \(wrapped\) in email messages. | 
| O365Defender.SafeLinks.Policy.DistinguishedName | String | Policy distinguished name \(DN\). | 
| O365Defender.SafeLinks.Policy.DoNotAllowClickThrough | Boolean | Whether users can click through the original URLs. | 
| O365Defender.SafeLinks.Policy.DoNotTrackUserClicks | Boolean | Whether user clicks are tracked. | 
| O365Defender.SafeLinks.Policy.DoNotRewriteUrls | Unknown | List of URLs that are not rewritten by Safe Links scanning. | 
| O365Defender.SafeLinks.Policy.EnableForInternalSenders | Boolean | Whether the Safe Links policy is applied to messages sent between internal senders and internal recipients within the same Exchange Online organization. | 
| O365Defender.SafeLinks.Policy.EnableOrganizationBranding | Boolean | whether the organization's logo is displayed on Safe Links warning and notification pages. | 
| O365Defender.SafeLinks.Policy.EnableSafeLinksForTeams | Boolean | Whether the Safe Link policy is enabled for Microsoft Teams. | 
| O365Defender.SafeLinks.Policy.ExchangeObjectId | String | Exchange object ID. | 
| O365Defender.SafeLinks.Policy.ExchangeVersion | String | The version o fthe Exchange server. | 
| O365Defender.SafeLinks.Policy.Guid | String | The GUID of the Safe Link policy. | 
| O365Defender.SafeLinks.Policy.Id | String | The ID of the Safe Link policy. | 
| O365Defender.SafeLinks.Policy.Identity | String | The indetity of the Safe Links policy. | 
| O365Defender.SafeLinks.Policy.IsDefault | Boolean | Whether the Safe Links policy is default. | 
| O365Defender.SafeLinks.Policy.IsEnabled | Boolean | Whether Safe Links protection is enabled for email messages or not. | 
| O365Defender.SafeLinks.Policy.IsValid | Boolean | Whether the Safe Links policy is valid. | 
| O365Defender.SafeLinks.Policy.Name | String | Policy name. | 
| O365Defender.SafeLinks.Policy.ObjectState | String | The Safe Link policy state. | 
| O365Defender.SafeLinks.Policy.OrganizationId | String | The ID | 
| O365Defender.SafeLinks.Policy.ScanUrls | Boolean | Whether real-time scanning of clicked links in email messages is enabled or not. | 
| O365Defender.SafeLinks.Policy.WhenChanged | Date | The date and time the Safe Link Policy was modified. Time format: YYYY-MM-DDThh:mm:ss\+00:00 | 
| O365Defender.SafeLinks.Policy.WhenChangedUTC | Date | The date and time \(in UTC\) the Policy was modified. Time format: YYYY-MM-DDTHH:MM:SSZ | 
| O365Defender.SafeLinks.Policy.WhenCreated | Date | The date and time the Safe Link Policy was created. Time format: YYYY-MM-DDThh:mm:ss\+00:00 | 
| O365Defender.SafeLinks.Policy.WhenCreatedUTC | Date | The date and time \(in UTC\) the Safe Link Policy was created. Time format: YYYY-MM-DDTHH:MM:SSZ | 


#### Command Example
```
{
  "O365Defender.SafeLinks.Policy(obj.Guid === val.Guid)": [
    {
      "AdminDisplayName": "Few URL",
      "AllowClickThrough": true,
      "CustomNotificationText": "Sorry, you cant click through this URL",
      "DeliverMessageAfterScan": false,
      "DisableUrlRewrite": false,
      "DistinguishedName": "CN=Policy2,CN=Safe Links,CN=Transport Settings,CN=Configuration,CN=xsoartest.onmicrosoft.com,CN=ConfigurationUnits,DC=EURPR07A123,DC=PROD,DC=OUTLOOK,DC=COM",
      "DoNotAllowClickThrough": false,
      "DoNotRewriteUrls": [
        "www.test.com",
        "https://xsoar.test.com"
      ],
      "DoNotTrackUserClicks": false,
      "EnableForInternalSenders": false,
      "EnableOrganizationBranding": false,
      "EnableSafeLinksForTeams": false,
      "ExchangeObjectId": "5796cea3-cfdb-4a99-9956-bf62209118a6",
      "ExchangeVersion": "0.20 (15.0.0.0)",
      "ExcludedUrls": [
        "www.test.com",
        "https://xsoar.test.com"
      ],
      "Guid": "5796cea3-cfdb-4a99-9956-bf62209118a6",
      "Id": "Policy2",
      "Identity": "Policy2",
      "IsBuiltInProtection": false,
      "IsDefault": false,
      "IsEnabled": true,
      "IsValid": true,
      "LocalizedNotificationTextList": [
        "[zh-Hant, 對不起，你不能點擊通過這個網址]",
        "[af, Jammer, jy kan nie deur hierdie URL klik nie]",
        "[hi, क्षमा करें, आप इस यूआरएल के माध्यम से क्लिक नहीं कर सकते]",
        "[ja, この URL をクリックできません。]",
        "[otq, Nä'ä di tsa̲hu̲, hingi tsa̲ o̲t'e clic nuna ar URL]",
        "[zh-Hans, 对不起，你不能点击通过这个网址]",
        "[ur, معذرت، آپ اس یو آر ایل کے ذریعے کلک نہیں کر سکتے]",
        "[ht, Padon, ou pa klike sou URL sa a]",
        "[it, Siamo spiacenti, non puoi fare clic su questo URL]",
        "[ms, Maaf, anda tidak boleh klik melalui URL ini]",
        "[bs, Žao mi je, ne možete kliknuti kroz ovaj URL]",
        "[cs, Je nám líto, ale nemůžete kliknout na tuto adresu URL]",
        "[mt, Jiddispjaċina, ma tistax tikklikkja permezz ta' dan il-URL]",
        "[fa, با عرض پوزش، شما نمی توانید از طریق این آدرس کلیک کنید]",
        "[ga, Ár leithscéal, ní féidir leat cliceáil tríd an URL seo]",
        "[da, Beklager, men du kan ikke klikke dig igennem denne URL-adresse]",
        "[hr, Nažalost, ne možete kliknuti kroz ovaj URL]",
        "[he, מצטערים, אתה לא יכול ללחוץ על כתובת URL זו]",
        "[et, Kahjuks ei saa te seda URL-i klõpsata]",
        "[tr, Üzgünüz, bu URL'yi tıklatamazsınız]",
        "[ru, Извините, вы не можете щелкнуть по этому URL-адресу]",
        "[nb, Beklager, du kan ikke klikke deg gjennom denne URL-adressen]",
        "[ar, عذرا، أنت غير قادر على النقر من خلال هذا العنوان]",
        "[fr, Désolé, vous ne pouvez pas cliquer sur cette URL]",
        "[sv, Tyvärr kan du inte klicka igenom den här URL:en]",
        "[tlh-Piqd,      ]",
        "[de, Es tut uns leid, aber Sie können sich nicht durch diese URL klicken]",
        "[id, Maaf, Anda tidak bisa mengklik URL ini]",
        "[kk, Кешіріңіз, осы URL мекенжайы арқылы басуға болмайды]",
        "[lv, Atvainojiet, jūs nevarat noklikšķināt caur šo URL]",
        "[yue, 对唔住，你唔可以點擊透過呢個網址]",
        "[nl, Sorry, u kunt niet door deze URL klikken]",
        "[ro, Ne pare rău, tu cant faceți clic prin acest URL-ul]",
        "[ml, ക്ഷമിക്കണം, ഈ യുആർഎൽ വഴി ക്ലിക്ക് ചെയ്യാൻ നിങ്ങൾക്ക് കഴിയില്ല]",
        "[sw, Samahani, unaweza kubofya kupitia URL hii]",
        "[sl, Žal ne morete klikati preko tega URL-ja]",
        "[th, ขออภัย คุณไม่สามารถคลิกผ่าน URL นี้]",
        "[to, Kātaki fakamolemole, he ʻikai lava ke ke lomiʻi ʻi he URL ko ʻení]",
        "[pt-PT, Desculpe, não pode clicar neste URL]",
        "[ca, Ho sentim, no podeu fer clic a través d'aquesta URL]",
        "[ko, 죄송합니다, 이 URL을 클릭할 수 없습니다.]",
        "[el, Δυστυχώς, δεν μπορείτε να κάνετε κλικ σε αυτήν τη διεύθυνση URL]",
        "[fil, Paumanhin, maaari mong i-click sa pamamagitan ng URL na ito]",
        "[fj, Vosota, e sega ni rawa ni o kiliki ena URL oqo]",
        "[cy, Mae'n ddrwg gennym, gallwch glicio drwy'r URL hwn]",
        "[hu, Sajnáljuk, nem kattinthat át ezen az URL-címen]",
        "[pt, Desculpe, você não pode clicar através desta URL]",
        "[kn, ಕ್ಷಮಿಸಿ, ಈ ಯುಆರ್ ಎಲ್ ಮೂಲಕ ನೀವು ಕ್ಲಿಕ್ ಮಾಡಲು ಸಾಧ್ಯವಿಲ್ಲ]",
        "[pl, Przepraszamy, nie możesz kliknąć tego adresu URL]",
        "[bn, দুঃখিত, আপনি এই ইউআরএল-এর মাধ্যমে ক্লিক করতে পারবেন না]",
        "[vi, Xin lỗi, bạn không thể nhấp qua URL này]",
        "[gu, માફ કરશો, તમે આ યુઆરએલ દ્વારા ક્લિક કરી શકતા નથી]",
        "[sr-Cyrl, Жао нам је, не можете кликнути кроз ову УРЛ адресу]",
        "[sr-Latn, Žao nam je, ne možete kliknuti kroz ovu URL adresu]",
        "[sk, Ľutujeme, nemôžete kliknúť na túto adresu URL]",
        "[en, Sorry, you cant click through this URL]",
        "[uk, На жаль, ви нахиляє натисніть через цю URL-адресу]",
        "[mi, Aroha mai, kāore e taea te pāwhiri mā tēnei URL]",
        "[sm, Faamalie atu, e le mafai ona e kiliki i le URL lenei]",
        "[fi, Valitettavasti et voi napsauttaa tätä URL-osoitetta]",
        "[lt, Atsiprašome, jūs negalite spustelėti per šį URL]",
        "[bg, Съжаляваме, можете да кликнете чрез този URL адрес]",
        "[te, క్షమించండి, ఈ యుఆర్ ఎల్ ద్వారా మీరు క్లిక్ చేయలేరు]",
        "[is, Því miður geturðu ekki smellt í gegnum þessa slóð]",
        "[ta, மன்னிக்கவும், இந்த யுஆர்எல் வழியாக கிளிக் செய்ய முடியாது]",
        "[tlh-Latn, taHqeq mIv'a' tIqwIj, qaStaHvIS poH nI''e']",
        "[mww, Thov txim, koj yuav nias los ntawm no URL]",
        "[es, Lo sentimos, no puedes hacer clic en esta URL]",
        "[pa, ਮਾਫ਼ ਕਰਨਾ, ਤੁਸੀਂ ਇਸ ਯੂਆਰਐਲ ਰਾਹੀਂ ਕਲਿੱਕ ਨਹੀਂ ਕਰ ਸਕਦੇ]",
        "[mg, Miala tsiny fa tsy afaka manindry ity URL ity ianao]"
      ],
      "Name": "Policy2",
      "ObjectCategory": "EURPR07A123.PROD.OUTLOOK.COM/Configuration/Schema/ms-Exch-Smart-Links-Protection-Config",
      "ObjectClass": [
        "top",
        "msExchSmartLinksProtectionConfig"
      ],
      "ObjectState": "Unchanged",
      "OrganizationId": "EURPR07A123.PROD.OUTLOOK.COM/Microsoft Exchange Hosted Organizations/xsoartest.onmicrosoft.com - EURPR07A123.PROD.OUTLOOK.COM/ConfigurationUnits/xsoartest.onmicrosoft.com/Configuration",
      "OrganizationalUnitRoot": "xsoartest.onmicrosoft.com",
      "OriginatingServer": "AM7PR07A05DC123.EURPR07A123.PROD.OUTLOOK.COM",
      "PSComputerName": "outlook.office365.com",
      "PSShowComputerName": false,
      "RecommendedPolicyType": "Custom",
      "RunspaceId": "8501abb8-6d7c-45ca-bc0d-4c260d68d248",
      "ScanUrls": false,
      "TrackClicks": true,
      "WhenChanged": "2021-10-21T12:49:09+00:00",
      "WhenChangedUTC": "2021-10-21T12:49:09Z",
      "WhenCreated": "2021-10-21T12:49:03+00:00",
      "WhenCreatedUTC": "2021-10-21T12:49:03Z",
      "WhiteListedUrls": "www.test.com,https://xsoar.test.com"
    }
  ]
}

```

#### Human Readable Output
>### Results of o365-defender-safelinks-policy-list
>| AdminDisplayName | AllowClickThrough | CustomNotificationText | DeliverMessageAfterScan | DisableUrlRewrite | DistinguishedName | DoNotAllowClickThrough | DoNotRewriteUrls | DoNotTrackUserClicks | EnableForInternalSenders | EnableOrganizationBranding | EnableSafeLinksForTeams | ExchangeObjectId | ExchangeVersion | ExcludedUrls | Guid | Id | Identity | IsBuiltInProtection | IsDefault | IsEnabled | IsValid | LocalizedNotificationTextList | Name | ObjectCategory | ObjectClass | ObjectState | OrganizationalUnitRoot | OrganizationId | OriginatingServer | PSComputerName | PSShowComputerName | RecommendedPolicyType | RunspaceId | ScanUrls | TrackClicks | WhenChanged | WhenChangedUTC | WhenCreated | WhenCreatedUTC | WhiteListedUrls
>| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
>| Few URL | true | Sorry, you cant click through this URL | false | false | CN=Policy2,CN=Safe Links,CN=Transport Settings,CN=Configuration,CN=xsoartest.onmicrosoft.com,CN=ConfigurationUnits,DC=EURPR07A123,DC=PROD,DC=OUTLOOK,DC=COM | false | ["www.test.com","https://xsoar.test.com"] | false | false | false | false | {"value":"5796cea3-cfdb-4a99-9956-bf62209118a6","Guid":"5796cea3-cfdb-4a99-9956-bf62209118a6"} | 0.20 (15.0.0.0) | ["www.test.com","https://xsoar.test.com"] | {"value":"5796cea3-cfdb-4a99-9956-bf62209118a6","Guid":"5796cea3-cfdb-4a99-9956-bf62209118a6"} | Policy2 | Policy2 | false | false | true | true | ["[zh-Hant, 對不起，你不能點擊通過這個網址]","[af, Jammer, jy kan nie deur hierdie URL klik nie]","[hi, क्षमा करें, आप इस यूआरएल के माध्यम से क्लिक नहीं कर सकते]","[ja, この URL をクリックできません。]","[otq, Nä'ä di tsa̲hu̲, hingi tsa̲ o̲t'e clic nuna ar URL]","[zh-Hans, 对不起，你不能点击通过这个网址]","[ur, معذرت، آپ اس یو آر ایل کے ذریعے کلک نہیں کر سکتے]","[ht, Padon, ou pa klike sou URL sa a]","[it, Siamo spiacenti, non puoi fare clic su questo URL]","[ms, Maaf, anda tidak boleh klik melalui URL ini]","[bs, Žao mi je, ne možete kliknuti kroz ovaj URL]","[cs, Je nám líto, ale nemůžete kliknout na tuto adresu URL]","[mt, Jiddispjaċina, ma tistax tikklikkja permezz ta' dan il-URL]","[fa, با عرض پوزش، شما نمی توانید از طریق این آدرس کلیک کنید]","[ga, Ár leithscéal, ní féidir leat cliceáil tríd an URL seo]","[da, Beklager, men du kan ikke klikke dig igennem denne URL-adresse]","[hr, Nažalost, ne možete kliknuti kroz ovaj URL]","[he, מצטערים, אתה לא יכול ללחוץ על כתובת URL זו]","[et, Kahjuks ei saa te seda URL-i klõpsata]","[tr, Üzgünüz, bu URL'yi tıklatamazsınız]","[ru, Извините, вы не можете щелкнуть по этому URL-адресу]","[nb, Beklager, du kan ikke klikke deg gjennom denne URL-adressen]","[ar, عذرا، أنت غير قادر على النقر من خلال هذا العنوان]","[fr, Désolé, vous ne pouvez pas cliquer sur cette URL]","[sv, Tyvärr kan du inte klicka igenom den här URL:en]","[tlh-Piqd,      ]","[de, Es tut uns leid, aber Sie können sich nicht durch diese URL klicken]","[id, Maaf, Anda tidak bisa mengklik URL ini]","[kk, Кешіріңіз, осы URL мекенжайы арқылы басуға болмайды]","[lv, Atvainojiet, jūs nevarat noklikšķināt caur šo URL]","[yue, 对唔住，你唔可以點擊透過呢個網址]","[nl, Sorry, u kunt niet door deze URL klikken]","[ro, Ne pare rău, tu cant faceți clic prin acest URL-ul]","[ml, ക്ഷമിക്കണം, ഈ യുആർഎൽ വഴി ക്ലിക്ക് ചെയ്യാൻ നിങ്ങൾക്ക് കഴിയില്ല]","[sw, Samahani, unaweza kubofya kupitia URL hii]","[sl, Žal ne morete klikati preko tega URL-ja]","[th, ขออภัย คุณไม่สามารถคลิกผ่าน URL นี้]","[to, Kātaki fakamolemole, he ʻikai lava ke ke lomiʻi ʻi he URL ko ʻení]","[pt-PT, Desculpe, não pode clicar neste URL]","[ca, Ho sentim, no podeu fer clic a través d'aquesta URL]","[ko, 죄송합니다, 이 URL을 클릭할 수 없습니다.]","[el, Δυστυχώς, δεν μπορείτε να κάνετε κλικ σε αυτήν τη διεύθυνση URL]","[fil, Paumanhin, maaari mong i-click sa pamamagitan ng URL na ito]","[fj, Vosota, e sega ni rawa ni o kiliki ena URL oqo]","[cy, Mae'n ddrwg gennym, gallwch glicio drwy'r URL hwn]","[hu, Sajnáljuk, nem kattinthat át ezen az URL-címen]","[pt, Desculpe, você não pode clicar através desta URL]","[kn, ಕ್ಷಮಿಸಿ, ಈ ಯುಆರ್ ಎಲ್ ಮೂಲಕ ನೀವು ಕ್ಲಿಕ್ ಮಾಡಲು ಸಾಧ್ಯವಿಲ್ಲ]","[pl, Przepraszamy, nie możesz kliknąć tego adresu URL]","[bn, দুঃখিত, আপনি এই ইউআরএল-এর মাধ্যমে ক্লিক করতে পারবেন না]","[vi, Xin lỗi, bạn không thể nhấp qua URL này]","[gu, માફ કરશો, તમે આ યુઆરએલ દ્વારા ક્લિક કરી શકતા નથી]","[sr-Cyrl, Жао нам је, не можете кликнути кроз ову УРЛ адресу]","[sr-Latn, Žao nam je, ne možete kliknuti kroz ovu URL adresu]","[sk, Ľutujeme, nemôžete kliknúť na túto adresu URL]","[en, Sorry, you cant click through this URL]","[uk, На жаль, ви нахиляє натисніть через цю URL-адресу]","[mi, Aroha mai, kāore e taea te pāwhiri mā tēnei URL]","[sm, Faamalie atu, e le mafai ona e kiliki i le URL lenei]","[fi, Valitettavasti et voi napsauttaa tätä URL-osoitetta]","[lt, Atsiprašome, jūs negalite spustelėti per šį URL]","[bg, Съжаляваме, можете да кликнете чрез този URL адрес]","[te, క్షమించండి, ఈ యుఆర్ ఎల్ ద్వారా మీరు క్లిక్ చేయలేరు]","[is, Því miður geturðu ekki smellt í gegnum þessa slóð]","[ta, மன்னிக்கவும், இந்த யுஆர்எல் வழியாக கிளிக் செய்ய முடியாது]","[tlh-Latn, taHqeq mIv'a' tIqwIj, qaStaHvIS poH nI''e']","[mww, Thov txim, koj yuav nias los ntawm no URL]","[es, Lo sentimos, no puedes hacer clic en esta URL]","[pa, ਮਾਫ਼ ਕਰਨਾ, ਤੁਸੀਂ ਇਸ ਯੂਆਰਐਲ ਰਾਹੀਂ ਕਲਿੱਕ ਨਹੀਂ ਕਰ ਸਕਦੇ]","[mg, Miala tsiny fa tsy afaka manindry ity URL ity ianao]"] | Policy2 | EURPR07A123.PROD.OUTLOOK.COM/Configuration/Schema/ms-Exch-Smart-Links-Protection-Config | ["top","msExchSmartLinksProtectionConfig"] | Unchanged | xsoartest.onmicrosoft.com | EURPR07A123.PROD.OUTLOOK.COM/Microsoft Exchange Hosted Organizations/xsoartest.onmicrosoft.com - EURPR07A123.PROD.OUTLOOK.COM/ConfigurationUnits/xsoartest.onmicrosoft.com/Configuration | AM7PR07A05DC123.EURPR07A123.PROD.OUTLOOK.COM | outlook.office365.com | false | Custom | {"value":"8501abb8-6d7c-45ca-bc0d-4c260d68d248","Guid":"8501abb8-6d7c-45ca-bc0d-4c260d68d248"} | false | true | {"value":"2021-10-21T12:49:09+00:00","DateTime":"Thursday, October 21, 2021 12:49:09 PM"} | {"value":"2021-10-21T12:49:09Z","DateTime":"Thursday, October 21, 2021 12:49:09 PM"} | {"value":"2021-10-21T12:49:03+00:00","DateTime":"Thursday, October 21, 2021 12:49:03 PM"} | {"value":"2021-10-21T12:49:03Z","DateTime":"Thursday, October 21, 2021 12:49:03 PM"} | www.test.com,https://xsoar.test.com



### o365-defender-safelinks-policy-create
***
Create a new Safe Links policy.


#### Base Command

`o365-defender-safelinks-policy-create`
#### Input

| **Argument Name** | **Description** | **Required** |
| --- | --- | --- |
| name | The Name parameter specifies a unique name for the Safe Links policy. | Required | 
| admin_display_name | The description for the policy. | Optional | 
| custom_notification_text | The custom notification text to show to users. | Optional | 
| deliver_message_after_scan | Whether to deliver email messages only after Safe Links scanning is complete. When true, messages that contain malicious links are not delivered. Default is false. Possible values are: true,false. | Optional | 
| do_not_allow_click_through | Whether to allow users to click through to the original URL on warning pages. Default is false. Possible values are: true,false. | Optional | 
| do_not_rewrite_urls | Comma-separated list of URLs that are not rewritten by Safe Links scanning. | Optional | 
| do_not_track_user_clicks | Whether to track user clicks related to Safe Links protection of links in email messages. Default is false. Possible values are: true,false. | Optional | 
| enable_for_internal_senders | Whether the Safe Links policy is applied to messages sent between internal senders and internal recipients within the same Exchange Online organization. Default is false. Possible values are: true,false. | Optional | 
| enable_organization_branding | Whether to display the organization's logo on Safe Links warning and notification pages. Default is false. Possible values are: true,false. | Optional | 
| enable_safe_links_for_teams | Whether to enable the Safe Links for Microsoft Teams. Default is false. Possible values are: true,false. | Optional | 
| is_enabled | Whether to enable Safe Links protection for email messages. Default is false. Possible values are: true,false. | Optional | 
| scan_urls | Whether to enable or disable real-time scanning of clicked links in email messages. Default is false. Possible values are: true,false. | Optional | 
| use_translated_notification_text | Whether to use Microsoft Translator to automatically localize the custom notification text that you specified with the CustomNotificationText parameter. Default is false. Possible values are: true,false. | Optional | 


#### Context Output

| **Path** | **Type** | **Description** |
| --- | --- | --- |
| O365Defender.SafeLinks.AdminDisplayName | String | Policy description. | 
| O365Defender.SafeLinks.Policy.AllowClickThrough | Boolean | Whether users are allowed to clicl through the original URL. | 
| O365Defender.SafeLinks.Policy.CustomNotificationText | String | The customized notification text to show to users. | 
| O365Defender.SafeLinks.Policy.DeliverMessageAfterScan | Boolean | Whether the mail is delivered after Safe Links scanning was complete or not. | 
| O365Defender.SafeLinks.Policy.DisableUrlRewrite | Boolean | Whether URLs are rewriten \(wrapped\) in email messages. | 
| O365Defender.SafeLinks.Policy.DistinguishedName | String | Policy distinguished name \(DN\). | 
| O365Defender.SafeLinks.Policy.DoNotAllowClickThrough | Boolean | Whether users can click through the original URLs. | 
| O365Defender.SafeLinks.Policy.DoNotTrackUserClicks | Boolean | Whether user clicks are tracked. | 
| O365Defender.SafeLinks.Policy.DoNotRewriteUrls | Unknown | List of URLs that are not rewritten by Safe Links scanning. | 
| O365Defender.SafeLinks.Policy.EnableForInternalSenders | Boolean | Whether the Safe Links policy is applied to messages sent between internal senders and internal recipients within the same Exchange Online organization. | 
| O365Defender.SafeLinks.Policy.EnableOrganizationBranding | Boolean | whether the organization's logo is displayed on Safe Links warning and notification pages. | 
| O365Defender.SafeLinks.Policy.EnableSafeLinksForTeams | Boolean | Whether the Safe Link policy is enabled for Microsoft Teams. | 
| O365Defender.SafeLinks.Policy.ExchangeObjectId | String | Exchange object ID. | 
| O365Defender.SafeLinks.Policy.ExchangeVersion | String | The version o fthe Exchange server. | 
| O365Defender.SafeLinks.Policy.Guid | String | The GUID of the Safe Link policy. | 
| O365Defender.SafeLinks.Policy.Id | String | The ID of the Safe Link policy. | 
| O365Defender.SafeLinks.Policy.Identity | String | The indetity of the Safe Links policy. | 
| O365Defender.SafeLinks.Policy.IsDefault | Boolean | Whether the Safe Links policy is default. | 
| O365Defender.SafeLinks.Policy.IsEnabled | Boolean | Whether Safe Links protection is enabled for email messages or not. | 
| O365Defender.SafeLinks.Policy.IsValid | Boolean | Whether the Safe Links policy is valid. | 
| O365Defender.SafeLinks.Policy.Name | String | Policy name. | 
| O365Defender.SafeLinks.Policy.ObjectState | String | The Safe Link policy state. | 
| O365Defender.SafeLinks.Policy.OrganizationId | String | The ID | 
| O365Defender.SafeLinks.Policy.ScanUrls | Boolean | Whether real-time scanning of clicked links in email messages is enabled or not. | 
| O365Defender.SafeLinks.Policy.WhenChanged | Date | The date and time the Safe Link Policy was modified. Time format: YYYY-MM-DDThh:mm:ss\+00:00 | 
| O365Defender.SafeLinks.Policy.WhenChangedUTC | Date | The date and time \(in UTC\) the Policy was modified. Time format: YYYY-MM-DDTHH:MM:SSZ | 
| O365Defender.SafeLinks.Policy.WhenCreated | Date | The date and time the Safe Link Policy was created. Time format: YYYY-MM-DDThh:mm:ss\+00:00 | 
| O365Defender.SafeLinks.Policy.WhenCreatedUTC | Date | The date and time \(in UTC\) the Safe Link Policy was created. Time format: YYYY-MM-DDTHH:MM:SSZ | 


#### Command Example
```{
  "O365Defender.SafeLinks.Policy(obj.Guid === val.Guid)": [
    {
      "AdminDisplayName": "Few URL",
      "AllowClickThrough": true,
      "CustomNotificationText": "Sorry, you cant click through this URL",
      "DeliverMessageAfterScan": false,
      "DisableUrlRewrite": false,
      "DistinguishedName": "CN=Policy2,CN=Safe Links,CN=Transport Settings,CN=Configuration,CN=xsoartest.onmicrosoft.com,CN=ConfigurationUnits,DC=EURPR07A123,DC=PROD,DC=OUTLOOK,DC=COM",
      "DoNotAllowClickThrough": false,
      "DoNotRewriteUrls": [
        "www.test.com",
        "https://xsoar.test.com"
      ],
      "DoNotTrackUserClicks": false,
      "EnableForInternalSenders": false,
      "EnableOrganizationBranding": false,
      "EnableSafeLinksForTeams": false,
      "ExchangeObjectId": "5796cea3-cfdb-4a99-9956-bf62209118a6",
      "ExchangeVersion": "0.20 (15.0.0.0)",
      "ExcludedUrls": [
        "www.test.com",
        "https://xsoar.test.com"
      ],
      "Guid": "5796cea3-cfdb-4a99-9956-bf62209118a6",
      "Id": "Policy2",
      "Identity": "Policy2",
      "IsBuiltInProtection": false,
      "IsDefault": false,
      "IsEnabled": true,
      "IsValid": true,
      "LocalizedNotificationTextList": [],
      "Name": "Policy2",
      "ObjectCategory": "EURPR07A123.PROD.OUTLOOK.COM/Configuration/Schema/ms-Exch-Smart-Links-Protection-Config",
      "ObjectClass": [
        "top",
        "msExchSmartLinksProtectionConfig"
      ],
      "ObjectState": "Unchanged",
      "OrganizationId": "EURPR07A123.PROD.OUTLOOK.COM/Microsoft Exchange Hosted Organizations/xsoartest.onmicrosoft.com - EURPR07A123.PROD.OUTLOOK.COM/ConfigurationUnits/xsoartest.onmicrosoft.com/Configuration",
      "OrganizationalUnitRoot": "xsoartest.onmicrosoft.com",
      "OriginatingServer": "AM7PR07A05DC123.EURPR07A123.PROD.OUTLOOK.COM",
      "PSComputerName": "outlook.office365.com",
      "PSShowComputerName": false,
      "RecommendedPolicyType": "Custom",
      "RunspaceId": "8501abb8-6d7c-45ca-bc0d-4c260d68d248",
      "ScanUrls": false,
      "TrackClicks": true,
      "WhenChanged": "2021-10-21T12:49:09+00:00",
      "WhenChangedUTC": "2021-10-21T12:49:09Z",
      "WhenCreated": "2021-10-21T12:49:03+00:00",
      "WhenCreatedUTC": "2021-10-21T12:49:03Z",
      "WhiteListedUrls": "www.test.com,https://xsoar.test.com"
    }
  ]
}

```

#### Human Readable Output
>### Results of o365-defender-safelinks-policy-list
>| AdminDisplayName | AllowClickThrough | CustomNotificationText | DeliverMessageAfterScan | DisableUrlRewrite | DistinguishedName | DoNotAllowClickThrough | DoNotRewriteUrls | DoNotTrackUserClicks | EnableForInternalSenders | EnableOrganizationBranding | EnableSafeLinksForTeams | ExchangeObjectId | ExchangeVersion | ExcludedUrls | Guid | Id | Identity | IsBuiltInProtection | IsDefault | IsEnabled | IsValid | LocalizedNotificationTextList | Name | ObjectCategory | ObjectClass | ObjectState | OrganizationalUnitRoot | OrganizationId | OriginatingServer | PSComputerName | PSShowComputerName | RecommendedPolicyType | RunspaceId | ScanUrls | TrackClicks | WhenChanged | WhenChangedUTC | WhenCreated | WhenCreatedUTC | WhiteListedUrls
>| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
>| Few URL | true | Sorry, you cant click through this URL | false | false | CN=Policy2,CN=Safe Links,CN=Transport Settings,CN=Configuration,CN=xsoartest.onmicrosoft.com,CN=ConfigurationUnits,DC=EURPR07A123,DC=PROD,DC=OUTLOOK,DC=COM | false | | Policy2 | EURPR07A123.PROD.OUTLOOK.COM/Configuration/Schema/ms-Exch-Smart-Links-Protection-Config | ["top","msExchSmartLinksProtectionConfig"] | Unchanged | xsoartest.onmicrosoft.com | EURPR07A123.PROD.OUTLOOK.COM/Microsoft Exchange Hosted Organizations/xsoartest.onmicrosoft.com - EURPR07A123.PROD.OUTLOOK.COM/ConfigurationUnits/xsoartest.onmicrosoft.com/Configuration | AM7PR07A05DC123.EURPR07A123.PROD.OUTLOOK.COM | outlook.office365.com | false | Custom | {"value":"8501abb8-6d7c-45ca-bc0d-4c260d68d248","Guid":"8501abb8-6d7c-45ca-bc0d-4c260d68d248"} | false | true | {"value":"2021-10-21T12:49:09+00:00","DateTime":"Thursday, October 21, 2021 12:49:09 PM"} | {"value":"2021-10-21T12:49:09Z","DateTime":"Thursday, October 21, 2021 12:49:09 PM"} | {"value":"2021-10-21T12:49:03+00:00","DateTime":"Thursday, October 21, 2021 12:49:03 PM"} | {"value":"2021-10-21T12:49:03Z","DateTime":"Thursday, October 21, 2021 12:49:03 PM"} | www.test.com,https://xsoar.test.com


### o365-defender-safelinks-policy-update
***
Update a Safe Links policy.


#### Base Command

`o365-defender-safelinks-policy-update`
#### Input

| **Argument Name** | **Description** | **Required** |
| --- | --- | --- |
| name | The Name parameter specifies a unique name for the Safe Links policy. | Required | 
| admin_display_name | The description for the policy. | Optional | 
| custom_notification_text | The custom notification text to show to users. | Optional | 
| deliver_message_after_scan | Whether to deliver email messages only after Safe Links scanning is complete. When true, messages that contain malicious links are not delivered. Default is false. Possible values are: true,false. | Optional | 
| do_not_allow_click_through | Whether to allow users to click through to the original URL on warning pages. Default is false. Possible values are: true,false. | Optional | 
| do_not_rewrite_urls | Comma-separated list of URLs that are not rewritten by Safe Links scanning. | Optional | 
| do_not_track_user_clicks | Whether to track user clicks related to Safe Links protection of links in email messages. Default is false. Possible values are: true,false. | Optional | 
| enable_for_internal_senders | Whether the Safe Links policy is applied to messages sent between internal senders and internal recipients within the same Exchange Online organization. Default is false. Possible values are: true,false. | Optional | 
| enable_organization_branding | Whether to display the organization's logo on Safe Links warning and notification pages. Default is false. Possible values are: true,false. | Optional | 
| enable_safe_links_for_teams | Whether to enable the Safe Links for Microsoft Teams. Default is false. Possible values are: true,false. | Optional | 
| is_enabled | Whether to enable Safe Links protection for email messages. Default is false. Possible values are: true,false. | Optional | 
| scan_urls | Whether to enable or disable real-time scanning of clicked links in email messages. Default is false. Possible values are: true,false. | Optional | 
| use_translated_notification_text | Whether to use Microsoft Translator to automatically localize the custom notification text that you specified with the CustomNotificationText parameter. Default is false. Possible values are: true,false. | Optional | 


#### Context Output

| **Path** | **Type** | **Description** |
| --- | --- | --- |
| O365Defender.SafeLinks.AdminDisplayName | String | Policy description. | 
| O365Defender.SafeLinks.Policy.AllowClickThrough | Boolean | Whether users are allowed to clicl through the original URL. | 
| O365Defender.SafeLinks.Policy.CustomNotificationText | String | The customized notification text to show to users. | 
| O365Defender.SafeLinks.Policy.DeliverMessageAfterScan | Boolean | Whether the mail is delivered after Safe Links scanning was complete or not. | 
| O365Defender.SafeLinks.Policy.DisableUrlRewrite | Boolean | Whether URLs are rewriten \(wrapped\) in email messages. | 
| O365Defender.SafeLinks.Policy.DistinguishedName | String | Policy distinguished name \(DN\). | 
| O365Defender.SafeLinks.Policy.DoNotAllowClickThrough | Boolean | Whether users can click through the original URLs. | 
| O365Defender.SafeLinks.Policy.DoNotTrackUserClicks | Boolean | Whether user clicks are tracked. | 
| O365Defender.SafeLinks.Policy.DoNotRewriteUrls | Unknown | List of URLs that are not rewritten by Safe Links scanning. | 
| O365Defender.SafeLinks.Policy.EnableForInternalSenders | Boolean | Whether the Safe Links policy is applied to messages sent between internal senders and internal recipients within the same Exchange Online organization. | 
| O365Defender.SafeLinks.Policy.EnableOrganizationBranding | Boolean | whether the organization's logo is displayed on Safe Links warning and notification pages. | 
| O365Defender.SafeLinks.Policy.EnableSafeLinksForTeams | Boolean | Whether the Safe Link policy is enabled for Microsoft Teams. | 
| O365Defender.SafeLinks.Policy.ExchangeObjectId | String | Exchange object ID. | 
| O365Defender.SafeLinks.Policy.ExchangeVersion | String | The version o fthe Exchange server. | 
| O365Defender.SafeLinks.Policy.Guid | String | The GUID of the Safe Link policy. | 
| O365Defender.SafeLinks.Policy.Id | String | The ID of the Safe Link policy. | 
| O365Defender.SafeLinks.Policy.Identity | String | The indetity of the Safe Links policy. | 
| O365Defender.SafeLinks.Policy.IsDefault | Boolean | Whether the Safe Links policy is default. | 
| O365Defender.SafeLinks.Policy.IsEnabled | Boolean | Whether Safe Links protection is enabled for email messages or not. | 
| O365Defender.SafeLinks.Policy.IsValid | Boolean | Whether the Safe Links policy is valid. | 
| O365Defender.SafeLinks.Policy.Name | String | Policy name. | 
| O365Defender.SafeLinks.Policy.ObjectState | String | The Safe Link policy state. | 
| O365Defender.SafeLinks.Policy.OrganizationId | String | The ID | 
| O365Defender.SafeLinks.Policy.ScanUrls | Boolean | Whether real-time scanning of clicked links in email messages is enabled or not. | 
| O365Defender.SafeLinks.Policy.WhenChanged | Date | The date and time the Safe Link Policy was modified. Time format: YYYY-MM-DDThh:mm:ss\+00:00 | 
| O365Defender.SafeLinks.Policy.WhenChangedUTC | Date | The date and time \(in UTC\) the Policy was modified. Time format: YYYY-MM-DDTHH:MM:SSZ | 
| O365Defender.SafeLinks.Policy.WhenCreated | Date | The date and time the Safe Link Policy was created. Time format: YYYY-MM-DDThh:mm:ss\+00:00 | 
| O365Defender.SafeLinks.Policy.WhenCreatedUTC | Date | The date and time \(in UTC\) the Safe Link Policy was created. Time format: YYYY-MM-DDTHH:MM:SSZ | 


#### Command Example
```{
  "O365Defender.SafeLinks.Policy(obj.Guid === val.Guid)": [
    {
      "AdminDisplayName": "Few URL",
      "AllowClickThrough": true,
      "CustomNotificationText": "Sorry, you cant click through this URL",
      "DeliverMessageAfterScan": false,
      "DisableUrlRewrite": false,
      "DistinguishedName": "CN=Policy2,CN=Safe Links,CN=Transport Settings,CN=Configuration,CN=xsoartest.onmicrosoft.com,CN=ConfigurationUnits,DC=EURPR07A123,DC=PROD,DC=OUTLOOK,DC=COM",
      "DoNotAllowClickThrough": false,
      "DoNotRewriteUrls": [
        "www.test.com",
        "https://xsoar.test.com"
      ],
      "DoNotTrackUserClicks": false,
      "EnableForInternalSenders": false,
      "EnableOrganizationBranding": false,
      "EnableSafeLinksForTeams": false,
      "ExchangeObjectId": "5796cea3-cfdb-4a99-9956-bf62209118a6",
      "ExchangeVersion": "0.20 (15.0.0.0)",
      "ExcludedUrls": [
        "www.test.com",
        "https://xsoar.test.com"
      ],
      "Guid": "5796cea3-cfdb-4a99-9956-bf62209118a6",
      "Id": "Policy2",
      "Identity": "Policy2",
      "IsBuiltInProtection": false,
      "IsDefault": false,
      "IsEnabled": true,
      "IsValid": true,
      "LocalizedNotificationTextList": [],
      "Name": "Policy2",
      "ObjectCategory": "EURPR07A123.PROD.OUTLOOK.COM/Configuration/Schema/ms-Exch-Smart-Links-Protection-Config",
      "ObjectClass": [
        "top",
        "msExchSmartLinksProtectionConfig"
      ],
      "ObjectState": "Unchanged",
      "OrganizationId": "EURPR07A123.PROD.OUTLOOK.COM/Microsoft Exchange Hosted Organizations/xsoartest.onmicrosoft.com - EURPR07A123.PROD.OUTLOOK.COM/ConfigurationUnits/xsoartest.onmicrosoft.com/Configuration",
      "OrganizationalUnitRoot": "xsoartest.onmicrosoft.com",
      "OriginatingServer": "AM7PR07A05DC123.EURPR07A123.PROD.OUTLOOK.COM",
      "PSComputerName": "outlook.office365.com",
      "PSShowComputerName": false,
      "RecommendedPolicyType": "Custom",
      "RunspaceId": "8501abb8-6d7c-45ca-bc0d-4c260d68d248",
      "ScanUrls": false,
      "TrackClicks": true,
      "WhenChanged": "2021-10-21T12:49:09+00:00",
      "WhenChangedUTC": "2021-10-21T12:49:09Z",
      "WhenCreated": "2021-10-21T12:49:03+00:00",
      "WhenCreatedUTC": "2021-10-21T12:49:03Z",
      "WhiteListedUrls": "www.test.com,https://xsoar.test.com"
    }
  ]
}

```

#### Human Readable Output
>### Results of o365-defender-safelinks-policy-list
>| AdminDisplayName | AllowClickThrough | CustomNotificationText | DeliverMessageAfterScan | DisableUrlRewrite | DistinguishedName | DoNotAllowClickThrough | DoNotRewriteUrls | DoNotTrackUserClicks | EnableForInternalSenders | EnableOrganizationBranding | EnableSafeLinksForTeams | ExchangeObjectId | ExchangeVersion | ExcludedUrls | Guid | Id | Identity | IsBuiltInProtection | IsDefault | IsEnabled | IsValid | LocalizedNotificationTextList | Name | ObjectCategory | ObjectClass | ObjectState | OrganizationalUnitRoot | OrganizationId | OriginatingServer | PSComputerName | PSShowComputerName | RecommendedPolicyType | RunspaceId | ScanUrls | TrackClicks | WhenChanged | WhenChangedUTC | WhenCreated | WhenCreatedUTC | WhiteListedUrls
>| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
>| Few URL | true | Sorry, you cant click through this URL | false | false | CN=Policy2,CN=Safe Links,CN=Transport Settings,CN=Configuration,CN=xsoartest.onmicrosoft.com,CN=ConfigurationUnits,DC=EURPR07A123,DC=PROD,DC=OUTLOOK,DC=COM | false | | Policy2 | EURPR07A123.PROD.OUTLOOK.COM/Configuration/Schema/ms-Exch-Smart-Links-Protection-Config | ["top","msExchSmartLinksProtectionConfig"] | Unchanged | xsoartest.onmicrosoft.com | EURPR07A123.PROD.OUTLOOK.COM/Microsoft Exchange Hosted Organizations/xsoartest.onmicrosoft.com - EURPR07A123.PROD.OUTLOOK.COM/ConfigurationUnits/xsoartest.onmicrosoft.com/Configuration | AM7PR07A05DC123.EURPR07A123.PROD.OUTLOOK.COM | outlook.office365.com | false | Custom | {"value":"8501abb8-6d7c-45ca-bc0d-4c260d68d248","Guid":"8501abb8-6d7c-45ca-bc0d-4c260d68d248"} | false | true | {"value":"2021-10-21T12:49:09+00:00","DateTime":"Thursday, October 21, 2021 12:49:09 PM"} | {"value":"2021-10-21T12:49:09Z","DateTime":"Thursday, October 21, 2021 12:49:09 PM"} | {"value":"2021-10-21T12:49:03+00:00","DateTime":"Thursday, October 21, 2021 12:49:03 PM"} | {"value":"2021-10-21T12:49:03Z","DateTime":"Thursday, October 21, 2021 12:49:03 PM"} | www.test.com,https://xsoar.test.com



### o365-defender-safelinks-policy-remove
***
Remove a Safe Links policy.


#### Base Command

`o365-defender-safelinks-policy-remove`
#### Input

| **Argument Name** | **Description** | **Required** |
| --- | --- | --- |
| identity | The Identity of the Safe Links policy that you want to remove. Available identity fields of the policy are: Name, Distinguished name (DN), GUID. | Required | 


#### Context Output

There is no context output for this command.

#### Command Example
``` ```

#### Human Readable Output



### o365-defender-safelinks-rule-list
***
List Safe Links rules in your cloud-based organization.


#### Base Command

`o365-defender-safelinks-rule-list`
#### Input

| **Argument Name** | **Description** | **Required** |
| --- | --- | --- |
| identity | The Identity of the Safe Links rule that you want to view. Available identity fields are: Name, Distinguished name (DN), GUID. | Optional | 
| state | The State of the rules. Possible values are Enabled and Disabled. Possible values are: Enabled,Disabled. | Optional | 


#### Context Output

| **Path** | **Type** | **Description** |
| --- | --- | --- |
| O365Defender.SafeLinks.Rule.Comments | Unknown | Informative comments for the rule, such as what the rule is used for or how it has changed over time. The length of the comment can't exceed 1024 characters. | 
| O365Defender.SafeLinks.Rule.Conditions | String | The rule condition. | 
| O365Defender.SafeLinks.Rule.Description | String | The description of the rule. | 
| O365Defender.SafeLinks.Rule.DistinguishedName | String | Rule distinguished name \(DN\). | 
| O365Defender.SafeLinks.Rule.ExceptIfRecipientDomainIs | Unknown | Recipients with email address in the specified domains are excluded. | 
| O365Defender.SafeLinks.Rule.ExceptIfSentTo | Unknown | Recipients to be excluded. | 
| O365Defender.SafeLinks.Rule.ExceptIfSentToMemberOf | Unknown | Recipients in these groups are excluded. | 
| O365Defender.SafeLinks.Rule.Exceptions | Unknown | Rule exceptions. | 
| O365Defender.SafeLinks.Rule.Guid | String | The GUID of the rule. | 
| O365Defender.SafeLinks.Rule.Identity | String | The indetity of the Safe Links rule. | 
| O365Defender.SafeLinks.Rule.IsValid | Boolean | Whether the rule is valid or not. | 
| O365Defender.SafeLinks.Rule.Name | String | Rule name. | 
| O365Defender.SafeLinks.Rule.ObjectState | String | The state of the rule. | 
| O365Defender.SafeLinks.Rule.Priority | Number | The priorty of the rule. | 
| O365Defender.SafeLinks.Rule.RecipientDomainIs | Unknown | List of domains that are included in the rule. | 
| O365Defender.SafeLinks.Rule.RuleVersion.Build | Number | Rule build number. | 
| O365Defender.SafeLinks.Rule.RunspaceId | String | Run space ID. | 
| O365Defender.SafeLinks.Rule.SafeLinksPolicy | String | The Safe Links policy that's associated with this Safe Links rule. | 
| O365Defender.SafeLinks.Rule.SentTo | Unknown | List of recipients included in the rule. | 
| O365Defender.SafeLinks.Rule.SentToMemberOf | Unknown | List of distribution groups, dynamic distribution groups, or mail-enabled security groups included in the rule. | 
| O365Defender.SafeLinks.Rule.State | String | The state of the rule. | 
| O365Defender.SafeLinks.Rule.WhenChanged | Date | The date and time the rule was modified. Time format: YYYY-MM-DDThh:mm:ss\+00:00 | 


#### Command Example
```
{
  "O365Defender.SafeLinks.Rule(obj.Guid === val.Guid)": {
    "Comments": null,
    "Conditions": [
      "Microsoft.Exchange.MessagingPolicies.Rules.Tasks.SentToPredicate"
    ],
    "Description": "If the message:\r\n\tIs sent to 'xsoartest@paloaltonetworks.com'\r\nTake the following actions:\r\n\tApply safe links policy \"Policy2\".\r\n",
    "DistinguishedName": "CN=Policy2,CN=SafeLinksVersioned,CN=Rules,CN=Transport Settings,CN=Configuration,CN=xsoartest.onmicrosoft.com,CN=ConfigurationUnits,DC=EURPR07A123,DC=PROD,DC=OUTLOOK,DC=COM",
    "ExceptIfRecipientDomainIs": null,
    "ExceptIfSentTo": null,
    "ExceptIfSentToMemberOf": null,
    "Exceptions": null,
    "ExchangeVersion": "0.1 (8.0.535.0)",
    "Guid": "e5764de3-5495-4512-93f5-fe96d579fbd9",
    "Identity": "Policy2",
    "ImmutableId": "e5764de3-5495-4512-93f5-fe96d579fbd9",
    "IsValid": true,
    "Name": "Policy2",
    "ObjectState": "Unchanged",
    "OrganizationId": "EURPR07A123.PROD.OUTLOOK.COM/Microsoft Exchange Hosted Organizations/xsoartest.onmicrosoft.com - EURPR07A123.PROD.OUTLOOK.COM/ConfigurationUnits/xsoartest.onmicrosoft.com/Configuration",
    "PSComputerName": "outlook.office365.com",
    "PSShowComputerName": false,
    "Priority": 2,
    "RecipientDomainIs": null,
    "RuleVersion": {
      "Build": 0,
      "Major": 14,
      "MajorRevision": 0,
      "Minor": 0,
      "MinorRevision": 0,
      "Revision": 0
    },
    "RunspaceId": "72b57693-0ddb-45b0-a44f-4d722a352635",
    "SafeLinksPolicy": "Policy2",
    "SentTo": [
      "xsoartest@paloaltonetworks.com"
    ],
    "SentToMemberOf": null,
    "State": "Enabled",
    "WhenChanged": "2021-10-21T12:49:40+00:00"
  }
}
 
```

#### Human Readable Output

>### Results of o365-defender-safelinks-rule-list
>| Comments | Conditions | Description | DistinguishedName | ExceptIfRecipientDomainIs | ExceptIfSentTo | ExceptIfSentToMemberOf | Exceptions | ExchangeVersion | Guid | Identity | ImmutableId | IsValid | Name | ObjectState | OrganizationId | Priority | PSComputerName | PSShowComputerName | RecipientDomainIs | RuleVersion | RunspaceId | SafeLinksPolicy | SentTo | SentToMemberOf | State | WhenChanged
>| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
>| Changed recipients | "Microsoft.Exchange.MessagingPolicies.Rules.Tasks.SentToPredicate" | If the message: Is sent to 'xsoartest@paloaltonetworks.com'\ Take the following actions: Apply safe links policy "Policy2".\  | CN=Policy2,CN=SafeLinksVersioned,CN=Rules,CN=Transport Settings,CN=Configuration,CN=xsoartest.onmicrosoft.com,CN=ConfigurationUnits,DC=EURPR07A123,DC=PROD,DC=OUTLOOK,DC=COM |  |  |  |  | 0.1 (8.0.535.0) | {"value":"e5764de3-5495-4512-93f5-fe96d579fbd9","Guid":"e5764de3-5495-4512-93f5-fe96d579fbd9"} | Policy2 | {"value":"e5764de3-5495-4512-93f5-fe96d579fbd9","Guid":"e5764de3-5495-4512-93f5-fe96d579fbd9"} | true | Policy2 | Unchanged | EURPR07A123.PROD.OUTLOOK.COM/Microsoft Exchange Hosted Organizations/xsoartest.onmicrosoft.com - EURPR07A123.PROD.OUTLOOK.COM/ConfigurationUnits/xsoartest.onmicrosoft.com/Configuration | 2 | outlook.office365.com | false |  | {"Major":14,"Minor":0,"Build":0,"Revision":0,"MajorRevision":0,"MinorRevision":0} | {"value":"72b57693-0ddb-45b0-a44f-4d722a352635","Guid":"72b57693-0ddb-45b0-a44f-4d722a352635"} | Policy2 | "xsoartest@paloaltonetworks.com" |  | Enabled | {"value":"2021-10-21T12:49:40+00:00","DateTime":"Thursday, October 21, 2021 12:49:40 PM"}



### o365-defender-safelinks-rule-create
***
Create a Safe Links rule in your cloud-based organization.


#### Base Command

`o365-defender-safelinks-rule-create`
#### Input

| **Argument Name** | **Description** | **Required** |
| --- | --- | --- |
| name | A unique name for the Safe Links rule. | Required | 
| safe_links_policy | The Safe Links policy to associate with this Safe Links rule. | Required | 
| comments | An informative comments for the rule, such as what the rule is used for or how it has changed over time. The length of the comment can't exceed 1024 characters. | Optional | 
| enabled | Whether the rule is enabled. Possible values are: true,false. | Optional | 
| except_if_recipient_domain_is | Specifies an exception that looks for recipients with email address in the specified domains. | Optional | 
| except_if_sent_to | Specifies an exception that looks for recipients in messages. | Optional | 
| except_if_sent_to_member_of | Specifies an exception that looks for messages sent to members of groups. | Optional | 
| priority | The priority value for the rule to determines the order of rule processing. A lower integer value indicates a higher priority, the value 0 is the highest priority, and rules can't have the same priority value. | Optional | 
| recipient_domain_is | Specifies a condition that looks for recipients with email address in the specified domains. | Optional | 
| sent_to | Specifies a condition that looks for recipients in messages. You can use any value that uniquely identifies the recipient. | Optional | 
| sent_to_member_of | Specifies a condition that looks for messages sent to members of distribution groups, dynamic distribution groups, or mail-enabled security groups. You can use any value that uniquely identifies the group. | Optional | 


#### Context Output

| **Path** | **Type** | **Description** |
| --- | --- | --- |
| O365Defender.SafeLinks.Rule.Comments | Unknown | Informative comments for the rule, such as what the rule is used for or how it has changed over time. The length of the comment can't exceed 1024 characters. | 
| O365Defender.SafeLinks.Rule.Conditions | String | The rule condition. | 
| O365Defender.SafeLinks.Rule.Description | String | The description of the rule. | 
| O365Defender.SafeLinks.Rule.DistinguishedName | String | Rule distinguished name \(DN\). | 
| O365Defender.SafeLinks.Rule.ExceptIfRecipientDomainIs | Unknown | Recipients with email address in the specified domains are excluded. | 
| O365Defender.SafeLinks.Rule.ExceptIfSentTo | Unknown | Recipients to be excluded. | 
| O365Defender.SafeLinks.Rule.ExceptIfSentToMemberOf | Unknown | Recipients in these groups are excluded. | 
| O365Defender.SafeLinks.Rule.Exceptions | Unknown | Rule exceptions. | 
| O365Defender.SafeLinks.Rule.Guid | String | The GUID of the rule. | 
| O365Defender.SafeLinks.Rule.Identity | String | The indetity of the Safe Links rule. | 
| O365Defender.SafeLinks.Rule.IsValid | Boolean | Whether the rule is valid or not. | 
| O365Defender.SafeLinks.Rule.Name | String | Rule name. | 
| O365Defender.SafeLinks.Rule.ObjectState | String | The state of the rule. | 
| O365Defender.SafeLinks.Rule.Priority | Number | The priorty of the rule. | 
| O365Defender.SafeLinks.Rule.RecipientDomainIs | Unknown | List of domains that are included in the rule. | 
| O365Defender.SafeLinks.Rule.RuleVersion.Build | Number | Rule build number. | 
| O365Defender.SafeLinks.Rule.RunspaceId | String | Run space ID. | 
| O365Defender.SafeLinks.Rule.SafeLinksPolicy | String | The Safe Links policy that's associated with this Safe Links rule. | 
| O365Defender.SafeLinks.Rule.SentTo | Unknown | List of recipients included in the rule. | 
| O365Defender.SafeLinks.Rule.SentToMemberOf | Unknown | List of distribution groups, dynamic distribution groups, or mail-enabled security groups included in the rule. | 
| O365Defender.SafeLinks.Rule.State | String | The state of the rule. | 
| O365Defender.SafeLinks.Rule.WhenChanged | Date | The date and time the rule was modified. Time format: YYYY-MM-DDThh:mm:ss\+00:00 | 


#### Command Example
```
{
  "O365Defender.SafeLinks.Rule(obj.Guid === val.Guid)": {
    "Comments": null,
    "Conditions": [
      "Microsoft.Exchange.MessagingPolicies.Rules.Tasks.SentToPredicate"
    ],
    "Description": "If the message:\r\n\tIs sent to 'xsoartest@paloaltonetworks.com'\r\nTake the following actions:\r\n\tApply safe links policy \"Policy2\".\r\n",
    "DistinguishedName": "CN=Policy2,CN=SafeLinksVersioned,CN=Rules,CN=Transport Settings,CN=Configuration,CN=xsoartest.onmicrosoft.com,CN=ConfigurationUnits,DC=EURPR07A123,DC=PROD,DC=OUTLOOK,DC=COM",
    "ExceptIfRecipientDomainIs": null,
    "ExceptIfSentTo": null,
    "ExceptIfSentToMemberOf": null,
    "Exceptions": null,
    "ExchangeVersion": "0.1 (8.0.535.0)",
    "Guid": "e5764de3-5495-4512-93f5-fe96d579fbd9",
    "Identity": "Policy2",
    "ImmutableId": "e5764de3-5495-4512-93f5-fe96d579fbd9",
    "IsValid": true,
    "Name": "Policy2",
    "ObjectState": "Unchanged",
    "OrganizationId": "EURPR07A123.PROD.OUTLOOK.COM/Microsoft Exchange Hosted Organizations/xsoartest.onmicrosoft.com - EURPR07A123.PROD.OUTLOOK.COM/ConfigurationUnits/xsoartest.onmicrosoft.com/Configuration",
    "PSComputerName": "outlook.office365.com",
    "PSShowComputerName": false,
    "Priority": 2,
    "RecipientDomainIs": null,
    "RuleVersion": {
      "Build": 0,
      "Major": 14,
      "MajorRevision": 0,
      "Minor": 0,
      "MinorRevision": 0,
      "Revision": 0
    },
    "RunspaceId": "72b57693-0ddb-45b0-a44f-4d722a352635",
    "SafeLinksPolicy": "Policy2",
    "SentTo": [
      "xsoartest@paloaltonetworks.com"
    ],
    "SentToMemberOf": null,
    "State": "Enabled",
    "WhenChanged": "2021-10-21T12:49:40+00:00"
  }
}
 
```

#### Human Readable Output
>### Results of o365-defender-safelinks-rule-create
>| Comments | Conditions | Description | DistinguishedName | ExceptIfRecipientDomainIs | ExceptIfSentTo | ExceptIfSentToMemberOf | Exceptions | ExchangeVersion | Guid | Identity | ImmutableId | IsValid | Name | ObjectState | OrganizationId | Priority | PSComputerName | PSShowComputerName | RecipientDomainIs | RuleVersion | RunspaceId | SafeLinksPolicy | SentTo | SentToMemberOf | State | WhenChanged
>| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
>| Changed recipients | "Microsoft.Exchange.MessagingPolicies.Rules.Tasks.SentToPredicate" | If the message: Is sent to 'xsoartest@paloaltonetworks.com'\ Take the following actions: Apply safe links policy "Policy2".\  | CN=Policy2,CN=SafeLinksVersioned,CN=Rules,CN=Transport Settings,CN=Configuration,CN=xsoartest.onmicrosoft.com,CN=ConfigurationUnits,DC=EURPR07A123,DC=PROD,DC=OUTLOOK,DC=COM |  |  |  |  | 0.1 (8.0.535.0) | {"value":"e5764de3-5495-4512-93f5-fe96d579fbd9","Guid":"e5764de3-5495-4512-93f5-fe96d579fbd9"} | Policy2 | {"value":"e5764de3-5495-4512-93f5-fe96d579fbd9","Guid":"e5764de3-5495-4512-93f5-fe96d579fbd9"} | true | Policy2 | Unchanged | EURPR07A123.PROD.OUTLOOK.COM/Microsoft Exchange Hosted Organizations/xsoartest.onmicrosoft.com - EURPR07A123.PROD.OUTLOOK.COM/ConfigurationUnits/xsoartest.onmicrosoft.com/Configuration | 2 | outlook.office365.com | false |  | {"Major":14,"Minor":0,"Build":0,"Revision":0,"MajorRevision":0,"MinorRevision":0} | {"value":"72b57693-0ddb-45b0-a44f-4d722a352635","Guid":"72b57693-0ddb-45b0-a44f-4d722a352635"} | Policy2 | "xsoartest@paloaltonetworks.com" |  | Enabled | {"value":"2021-10-21T12:49:40+00:00","DateTime":"Thursday, October 21, 2021 12:49:40 PM"}



### o365-defender-safelinks-rule-update
***
Update a given Safe Links rule.


#### Base Command

`o365-defender-safelinks-rule-update`
#### Input

| **Argument Name** | **Description** | **Required** |
| --- | --- | --- |
| name | A unique name for the Safe Links rule. | Required | 
| safe_links_policy | The Safe Links policy to associate with this Safe Links rule. | Required | 
| comments | An informative comments for the rule, such as what the rule is used for or how it has changed over time. The length of the comment can't exceed 1024 characters. | Optional | 
| enabled | Whether the rule is enabled. Possible values are: true,false. | Optional | 
| except_if_recipient_domain_is | Specifies an exception that looks for recipients with email address in the specified domains. | Optional | 
| except_if_sent_to | Specifies an exception that looks for recipients in messages. | Optional | 
| except_if_sent_to_member_of | Specifies an exception that looks for messages sent to members of groups. | Optional | 
| priority | The priority value for the rule to determines the order of rule processing. A lower integer value indicates a higher priority, the value 0 is the highest priority, and rules can't have the same priority value. | Optional | 
| recipient_domain_is | Specifies a condition that looks for recipients with email address in the specified domains. | Optional | 
| sent_to | Specifies a condition that looks for recipients in messages. You can use any value that uniquely identifies the recipient. | Optional | 
| sent_to_member_of | Specifies a condition that looks for messages sent to members of distribution groups, dynamic distribution groups, or mail-enabled security groups. You can use any value that uniquely identifies the group. | Optional | 


#### Context Output

| **Path** | **Type** | **Description** |
| --- | --- | --- |
| O365Defender.SafeLinks.Rule.Comments | Unknown | Informative comments for the rule, such as what the rule is used for or how it has changed over time. The length of the comment can't exceed 1024 characters. | 
| O365Defender.SafeLinks.Rule.Conditions | String | The rule condition. | 
| O365Defender.SafeLinks.Rule.Description | String | The description of the rule. | 
| O365Defender.SafeLinks.Rule.DistinguishedName | String | Rule distinguished name \(DN\). | 
| O365Defender.SafeLinks.Rule.ExceptIfRecipientDomainIs | Unknown | Recipients with email address in the specified domains are excluded. | 
| O365Defender.SafeLinks.Rule.ExceptIfSentTo | Unknown | Recipients to be excluded. | 
| O365Defender.SafeLinks.Rule.ExceptIfSentToMemberOf | Unknown | Recipients in these groups are excluded. | 
| O365Defender.SafeLinks.Rule.Exceptions | Unknown | Rule exceptions. | 
| O365Defender.SafeLinks.Rule.Guid | String | The GUID of the rule. | 
| O365Defender.SafeLinks.Rule.Identity | String | The indetity of the Safe Links rule. | 
| O365Defender.SafeLinks.Rule.IsValid | Boolean | Whether the rule is valid or not. | 
| O365Defender.SafeLinks.Rule.Name | String | Rule name. | 
| O365Defender.SafeLinks.Rule.ObjectState | String | The state of the rule. | 
| O365Defender.SafeLinks.Rule.Priority | Number | The priorty of the rule. | 
| O365Defender.SafeLinks.Rule.RecipientDomainIs | Unknown | List of domains that are included in the rule. | 
| O365Defender.SafeLinks.Rule.RuleVersion.Build | Number | Rule build number. | 
| O365Defender.SafeLinks.Rule.RunspaceId | String | Run space ID. | 
| O365Defender.SafeLinks.Rule.SafeLinksPolicy | String | The Safe Links policy that's associated with this Safe Links rule. | 
| O365Defender.SafeLinks.Rule.SentTo | Unknown | List of recipients included in the rule. | 
| O365Defender.SafeLinks.Rule.SentToMemberOf | Unknown | List of distribution groups, dynamic distribution groups, or mail-enabled security groups included in the rule. | 
| O365Defender.SafeLinks.Rule.State | String | The state of the rule. | 
| O365Defender.SafeLinks.Rule.WhenChanged | Date | The date and time the rule was modified. Time format: YYYY-MM-DDThh:mm:ss\+00:00 | 


#### Command Example
```
{
  "O365Defender.SafeLinks.Rule(obj.Guid === val.Guid)": {
    "Comments": null,
    "Conditions": [
      "Microsoft.Exchange.MessagingPolicies.Rules.Tasks.SentToPredicate"
    ],
    "Description": "If the message:\r\n\tIs sent to 'xsoartest@paloaltonetworks.com'\r\nTake the following actions:\r\n\tApply safe links policy \"Policy2\".\r\n",
    "DistinguishedName": "CN=Policy2,CN=SafeLinksVersioned,CN=Rules,CN=Transport Settings,CN=Configuration,CN=xsoartest.onmicrosoft.com,CN=ConfigurationUnits,DC=EURPR07A123,DC=PROD,DC=OUTLOOK,DC=COM",
    "ExceptIfRecipientDomainIs": null,
    "ExceptIfSentTo": null,
    "ExceptIfSentToMemberOf": null,
    "Exceptions": null,
    "ExchangeVersion": "0.1 (8.0.535.0)",
    "Guid": "e5764de3-5495-4512-93f5-fe96d579fbd9",
    "Identity": "Policy2",
    "ImmutableId": "e5764de3-5495-4512-93f5-fe96d579fbd9",
    "IsValid": true,
    "Name": "Policy2",
    "ObjectState": "Unchanged",
    "OrganizationId": "EURPR07A123.PROD.OUTLOOK.COM/Microsoft Exchange Hosted Organizations/xsoartest.onmicrosoft.com - EURPR07A123.PROD.OUTLOOK.COM/ConfigurationUnits/xsoartest.onmicrosoft.com/Configuration",
    "PSComputerName": "outlook.office365.com",
    "PSShowComputerName": false,
    "Priority": 2,
    "RecipientDomainIs": null,
    "RuleVersion": {
      "Build": 0,
      "Major": 14,
      "MajorRevision": 0,
      "Minor": 0,
      "MinorRevision": 0,
      "Revision": 0
    },
    "RunspaceId": "72b57693-0ddb-45b0-a44f-4d722a352635",
    "SafeLinksPolicy": "Policy2",
    "SentTo": [
      "xsoartest@paloaltonetworks.com"
    ],
    "SentToMemberOf": null,
    "State": "Enabled",
    "WhenChanged": "2021-10-21T12:49:40+00:00"
  }
}
 
```

#### Human Readable Output
>### Results of o365-defender-safelinks-rule-update
>| Comments | Conditions | Description | DistinguishedName | ExceptIfRecipientDomainIs | ExceptIfSentTo | ExceptIfSentToMemberOf | Exceptions | ExchangeVersion | Guid | Identity | ImmutableId | IsValid | Name | ObjectState | OrganizationId | Priority | PSComputerName | PSShowComputerName | RecipientDomainIs | RuleVersion | RunspaceId | SafeLinksPolicy | SentTo | SentToMemberOf | State | WhenChanged
>| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
>| Changed recipients | "Microsoft.Exchange.MessagingPolicies.Rules.Tasks.SentToPredicate" | If the message: Is sent to 'xsoartest@paloaltonetworks.com'\ Take the following actions: Apply safe links policy "Policy2".\  | CN=Policy2,CN=SafeLinksVersioned,CN=Rules,CN=Transport Settings,CN=Configuration,CN=xsoartest.onmicrosoft.com,CN=ConfigurationUnits,DC=EURPR07A123,DC=PROD,DC=OUTLOOK,DC=COM |  |  |  |  | 0.1 (8.0.535.0) | {"value":"e5764de3-5495-4512-93f5-fe96d579fbd9","Guid":"e5764de3-5495-4512-93f5-fe96d579fbd9"} | Policy2 | {"value":"e5764de3-5495-4512-93f5-fe96d579fbd9","Guid":"e5764de3-5495-4512-93f5-fe96d579fbd9"} | true | Policy2 | Unchanged | EURPR07A123.PROD.OUTLOOK.COM/Microsoft Exchange Hosted Organizations/xsoartest.onmicrosoft.com - EURPR07A123.PROD.OUTLOOK.COM/ConfigurationUnits/xsoartest.onmicrosoft.com/Configuration | 2 | outlook.office365.com | false |  | {"Major":14,"Minor":0,"Build":0,"Revision":0,"MajorRevision":0,"MinorRevision":0} | {"value":"72b57693-0ddb-45b0-a44f-4d722a352635","Guid":"72b57693-0ddb-45b0-a44f-4d722a352635"} | Policy2 | "xsoartest@paloaltonetworks.com" |  | Enabled | {"value":"2021-10-21T12:49:40+00:00","DateTime":"Thursday, October 21, 2021 12:49:40 PM"}

