---
layout: post
title: Intent Study Record
category: Android
tags: [Android]
---

# Intent
[Android Delveloper 'Intent' 한글사이트](https://developer.android.com/guide/components/intents-filters?hl=ko)
<br/>
<br/>
위 사이트 내 <br/>
3 line의 <strong>'● 액티비티 시작:'</strong> 에서 `startActivity()`가 나오면서 궁금해서 이 함수를 찾아봄<br/>
Intent의 액티비티 시작 관련은 이 [사이트](https://developer.android.com/training/basics/firstapp/starting-activity?hl=ko)도 
있으니 참고만 바람 ★나중에<br/>
<br/>

## startActivity(Intent)
- 'Context'에 속한 함수로 [레퍼런스](https://developer.android.com/reference/android/content/Context.html?hl=ko#startActivity(android.content.Intent))
- 파라미터만 다른 오버로딩 함수 하나 더 있음 <strong>startActivity(Intent, Bundle)</strong>
- +) 여러개 실행시키는 startActivities()함수도 있으니 ★나중에 확인바람

## startActivity(Intent, Bundle)
- 이 함수의 [레퍼런스](https://developer.android.com/reference/android/content/Context.html?hl=ko#startActivity(android.content.Intent,%2520android.os.Bundle))에서<br/><br/>
" Note that if this method is being called from outside of an Activity Context, <br/>
  then the Intent must include the Intent#FLAG_ACTIVITY_NEW_TASK launch flag. " <br/><br/>
  라는데 앞 절을 못알아 듣겠어서 FLAG_ACTIVITY_NEW_TASK를 찾아 유추해보기로 함
- Intent#FLAG_ACTIVITY_NEW_TASK 사용이유 : <br/>
   기존 액티비티에서 시작하지 않고 새 액티비티를 배치 할 기존 작업이 없기 때문에 별도의 작업을 수행해야하기 때문이라고 한다.

## startActivityForResult(Intent, int requestCode)
- 액티비티 실행시 사용되면 부를 수 있는 또 다른 함수, 얘는 새로 보여줄 액티비티가 종료될때 그 결과값을 caller인 액티비티가 수신해야할때 부른다. 
- [레퍼런스](https://developer.android.com/reference/android/app/Activity.html?hl=ko#startActivityForResult(android.content.Intent,%20int))
- [이 함수의 동작과정 이론적 설명 블로그1](https://developljy.tistory.com/16)
- [이 함수의 동작과정 예제 및 기술적 설명 블로그1](https://liveonthekeyboard.tistory.com/entry/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-startActivityForResult-onActivityResult-%EC%82%AC%EC%9A%A9%EB%B2%95)
- 새로 보여줄 액티비티에서 결과값 저장시,<br/>
  <strong>public final void setResult (int resultCode, Intent data)</strong>함수를 사용
  
  
### setResult (int resultCode, Intent data)
- [레퍼런스](https://developer.android.com/reference/android/app/Activity.html?hl=ko#setResult(int))
 내 하기 부분 어려운데 ★ 나중에 인텐트 플래그 배우고 나서 다시 한 번 봐줘~!<br/>
<br/>
" As of Build.VERSION_CODES.GINGERBREAD, the Intent you supply here can have Intent#FLAG_GRANT_READ_URI_PERMISSION <br/>
and/or Intent#FLAG_GRANT_WRITE_URI_PERMISSION set. <br/>
This will grant the Activity receiving the result access to the specific URIs in the Intent. <br/>
Access will remain until the Activity has finished (it will remain across the hosting process being killed and other temporary destruction)<br/>
and will be added to any existing set of URI permissions it already holds."<br/>
<br/>
- resultCode값은 Activity의 상수값(=Const=Constant)값을 쓰는데<br/>
  `RESULT_CANCELED`, `RESULT_OK`, `RESULT_FIRST_USER`가 있다.<br/>
  그 중 <strong>RESULT_FIRST_USER</strong>가 이해가 안가는데 [여기](https://stackoverflow.com/a/49225512)에 설명해놓았지만,
  사용자 정의값(=custom값)으로써<br/> 
  OS 수준과 앱 수준에서 설정된 상수간에 충돌이 발생하지 않게 `RESULT_FIRST_USER`값에 [offset](http://www.terms.co.kr/offset.htm)을 더해 사용자 정의값을 만들 수 있게 해주는 것으로 이해함!
  
<br/>
<br/>
### FLAG_ACTIVITY_NEW_TASK
- Task에 관한 이해가 선필요하므로 ['작업 및 백 스택' 레퍼런스](https://developer.android.com/guide/components/tasks-and-back-stack?hl=ko)부터 참조해야할 것 같음 ★나중에
- [레퍼런스](https://developer.android.com/reference/android/content/Intent.html?hl=ko#FLAG_ACTIVITY_NEW_TASK) ★나중에
- [찾아본 블로그 설명](http://theeye.pe.kr/archives/1298)이나 <strong>affinity</strong>에 대한 이해 필요함  ★나중에
- [조심해서 사용하라고 함](https://steemit.com/android/@kingori2/intent-flagactivitynewtask)  ★나중에
<br/>
오버로딩 함수에서 전달하는 <strong>Bundle</strong>이 궁금해짐<br/>
<br/>
### Bundle 
- : 어떻게 Activity를 시작해야할지에 관한 추가적인 옵션값
- startActivity(Intent, Bundle)에서 Bundle값으로 null을 줄 경우, no option
- See [ActivityOptions](https://developer.android.com/reference/android/app/ActivityOptions.html?hl=ko) for how to build the Bundle supplied here; ★나중에


### affinity 
★나중에


★나중에 다른 컴포넌트 공부할때 같이 봐줘야할 것들 -------------------------------------------
## Service
public boolean bindService (Intent service, 
                int flags, 
                Executor executor, 
                ServiceConnection conn) 함수에서 <strong>Executor</strong>에 관하여<br/>
[레퍼런스](https://developer.android.com/reference/android/content/Context.html?hl=ko#bindService(android.content.Intent,%20android.content.ServiceConnection,%20int))
                
## BroadcastReceiver
- sendOrderedBroadcast() 동작에 관해 더 자세히 [레퍼런스](https://developer.android.com/reference/android/content/Context.html?hl=ko#sendOrderedBroadcast(android.content.Intent,%2520java.lang.String,%2520android.content.BroadcastReceiver,%2520android.os.Handler,%2520int,%2520java.lang.String,%2520android.os.Bundle))
- [설명 블로그](https://abydos.tistory.com/26)


### MIME 타입
- [정의](https://dololak.tistory.com/130)


### 명시적 암시적 인텐트 설명
- [참조한 블로그 설명](https://limkydev.tistory.com/35)

### broadcast 설명
- [BoadcastReceiver는 메인스레드에서 실행, 10초 내 return되지 않으면 system이 receiver를 죽이거나 ANR 발생시킴](https://sunflaur.tistory.com/260)
- [sendOrderedBroadcast() 설명 블로그](https://abydos.tistory.com/26)

## Intent Filter
- [잘 설명해 놓은 블로그](https://www.charlezz.com/?p=859)
- [인텐트 필터와 그 하위 요소](https://www.charlezz.com/?p=859)

### URI
- [URI, URL, URN 설명](https://mygumi.tistory.com/139)
- [URI, URL, URN, IRI 설명](https://blog.naver.com/PostView.nhn?blogId=itperson&logNo=220838401501&categoryNo=50&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=search)
- [URI이지만 URL과 URN이 아닌 예](http://sunychoi.github.io/java/2015/04/27/uri-url.html)

## Intent Extra
- [intent.putExtra("data", data) vs intent.putExtras(bundle);](https://youngest-programming.tistory.com/50)
- [무엇이 더 빠릅니까? 하나의 intent.putExtras (문자열로 묶음) 또는 많은 intent.putExtra (문자열)?](https://stackoverflow.com/questions/17991288/what-is-faster-one-intent-putextrasbundle-with-strings-or-many-intent-putextr?noredirect=1&lq=1)

## Intent 전달되는 Uri 사용예시
- [Content 의 Uri 로부터 FilePath 가져오기 ](https://crystalcube.co.kr/184)
- [intent 와 Uri 를 이용해 인터넷 브라우저와 전화 앱 접근하기](https://appcafe.tistory.com/29)

## Intent 상수(Constants)값들 보기!!
- [Activity 생성시에 사용되는 Intent Flag 정리](http://theeye.pe.kr/archives/1298)
- [Intent 상수(Constants)값들](https://kairo96.gitbooks.io/android/content/ch2.8.html)


## resolveActivity()함수 호출 필요여부
- [resolveActivity() 레퍼런스](https://developer.android.com/reference/android/content/Intent.html?hl=ko#resolveActivity(android.content.pm.PackageManager))에서는 <br/>
  "This API is called for you as part of starting an activity from an intent. You do not normally need to call it yourself."라고
  부를 필요없다고 하는데,
- [암시적 Intent 설명](https://developer.android.com/guide/components/intents-filters?hl=ko#ExampleSend)의 주의사항에서는 확인하라고 하는거지??

- +) 더불어, [resolveActivity() 레퍼런스](https://developer.android.com/reference/android/content/Intent.html?hl=ko#resolveActivity(android.content.pm.PackageManager)) 영어도 해석바람
- +) "This method is implemented simply by calling PackageManager#resolveActivity with the "defaultOnly" parameter true."에서<br/>
   `PackageManager#resolveActivity` 함수도 정의 부분 봐야함!
   
## Intent.CATEGORY_DEFAULT
- `암시적 인텐트`를 수신받을 (서비스 아닌) 앱 구성요소가 반드시 Intent filter에 가지고 있어야하는 category값
- "android.intent.category.DEFAULT"
- [쉬운 설명](https://stackoverflow.com/a/21257097)

## PendingIntent
- [쉬운 설명](https://huewu.blog.me/110084228131)
- [Intent를 직접 보내지 않고 다른 클래스에게 Intent를 위임해주기 위한 클래스 정도](http://mar7r.blogspot.com/2013/07/pendingintent.html)
- [깔끔한 간략 설명 및 이미지](https://www.charlezz.com/?p=861)
- [상세한 설명 및 사용예](https://techlog.gurucat.net/80)
- [PendingIntent flags값 몇몇개](https://huewu.blog.me/110084228131)
- [안드로이드 PendingIntent Flag 의미](https://lucas-look.tistory.com/39)
- [whats-requestcode-used-for-on-pendingintent?](https://stackoverflow.com/questions/21526319/whats-requestcode-used-for-on-pendingintent)
- 
