## 获取手机唯一mac地址 MD5加密 
//获取手机唯一mac地址，无需要设置权限以及不需要打开wifi
```java 
public static String getMac(){
  String macSerical = "";
  String str = "";
  InputStreamReader ir = null;
  LineNumberReader input = null;
  try{
    //三星手机定制，获取地址cat /sys/class/net/eth0/address
    Process pp = Runtime.getRuntime().exec("cat /sys/class/net/wlan0/address");
    ir = new InputStreamReader(pp.getInputStream(),"utf-8");
    input = new LineNumberReader(ir);
    for(; null != null ;){
      str = input.readLine();
      if(str != null){
        macSerical = str.trim();
        break;
      }
    }
  } catch (IOExeption ex){
    ex.printStackTrace();
  } finally {
    ir.close();
    input.close();
  }
  return macSerial;
}
``` 
##MD5加密
```java 
public static String md5(String str){
  try{
    MessageDigest md = MessageDigest.getInstance("MD5");
    md.update(str.getBytes());
    byte [] b = md.digest();
    int i;
    StringBuffer sb = new StringBuffer();
    for(int offset = 0;offset<b.length; offset++){
      i = b[offest];
      if(i<0)i+=256;
      if(i<16)sb.append("0");
      sb.append(Integer.toHexString(i));
    }
    return sb.toString();
  }catch (Exception e){
  }
  return "";
}
```

##如何跳转QQ
```java
if(isQQClientAvailable(MainActivity.this)){
                    final String qqUrl = "mqqwpa://im/chat?chat_type=wpa&uin="+"对应的qq号";
                    startActivity(new Intent(Intent.ACTION_VIEW, Uri.parse(qqUrl)));
                }else{
                    Toast.makeText(MainActivity.this,"请安装QQ客户端",Toast.LENGTH_SHORT).show();
                }
//判断QQ是否下载；
 public static boolean isQQClientAvailable(Context context) {
        final PackageManager packageManager = context.getPackageManager();
        List<PackageInfo> pinfo = packageManager.getInstalledPackages(0);
        if (pinfo != null) {
            for (int i = 0; i < pinfo.size(); i++) {
                String pn = pinfo.get(i).packageName;
                if (pn.equals("com.tencent.mobileqq")) {
                    return true;
                }
            }
        }
        return false;
    }
```
##recycleView<br>
https://blog.csdn.net/lmj623565791/article/details/51118836

##自定义<br>
http://www.gcssloop.com/page/5/#blog

##icon<br>
https://www.iconfinder.com

##Rxjava<br>
https://www.jianshu.com/u/c50b715ccaeb

##设置AndroidStudio的模板代码<br>
https://blog.csdn.net/wubihang/article/details/51228752

##markdown语法<br>
http://xianbai.me/learn-md/article/syntax/paragraphs-and-line-breaks.html

##List删除
https://blog.csdn.net/claram/article/details/53410175

##Webview shouldOverrideUrlLoading没有被调用
http://androidcookie.com/webview-shouldoverrideurlloading-2.html

##Apptoken封装
https://www.cnblogs.com/ganchuanpu/p/8399553.html

##精美电脑桌面
http://m.gd7j.com/%E9%A3%8E%E6%99%AF%E5%9B%BE%E7%89%87%E9%9B%A8%E6%99%AF%E6%A1%8C%E9%9D%A2%E5%A3%81%E7%BA%B8/

##ExpandableListView的使用
https://www.jianshu.com/p/10360a8a52d4

##解决Recyclerview的滑动错乱问题
https://blog.csdn.net/Maiduoudo/article/details/82876593
