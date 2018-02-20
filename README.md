## 获取手机唯一mac地址
//获取手机唯一mac地址，无需要设置权限以及不需要打开wifi
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
