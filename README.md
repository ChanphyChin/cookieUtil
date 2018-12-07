## cookieUtil
```javascript
  /**
   * Created by Chanphy on 2018.12.7
   * cookie操作工具
   * 设置cookie：window.GI.CookieUtil.setCookie(cookieName: String, value: Any, time: Number(Time stamp))
   * 获取cookie：window.GI.CookieUtil.getCookie(cookieName: String)
   * 删除cookie：window.GI.CookieUtil.removeCookie(cookieName: String)
   */
  export class CookieUtil {

      static setCookie(name, value, time = 200000) {
          var exp = new Date();
          exp.setTime(exp.getTime() + time);
          document.cookie = name + "="+ escape (value) + ";expires=" + exp.toGMTString();
      }

      static getCookie(name) {
          var arr,reg=new RegExp("(^| )"+name+"=([^;]*)(;|$)");
          if(arr=document.cookie.match(reg)){
              return unescape(arr[2]);
          }else{
              return null;
          }
      }

      static removeCookie(name) {
          this.getCookie(name) && this.setCookie(name, null, -1);
      }
  };

```
