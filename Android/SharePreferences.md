## SharePreferences

SharedPreferences，它是一个轻量级的存储类，特别适合用于保存软件配置参数。
用SharedPreferences保存数据，其实是用xml文件存放数据，文件存放在/data/data/<package name>/shared_prefs目录下
getSharedPreferences (String name,int mode)
go through an SharedPreferences.Editor object

SharedPreferences.OnSharedPreferenceChangeListener
、、、
简单的存储示例：
SharedPreferences sharedPreferences = getSharedPreferences("fileName, Context.MODE_PRIVATE); //私有数据
Editor editor = sharedPreferences.edit();//获取编辑器
editor.putString("key", "key");
editor.putInt("age", 4);
editor.commit();//提交修改

生成fileName.xml文件内容如下：
<?xml version='1.0' encoding='utf-8' standalone='yes' ?>
<map>
<string name="key">key</string>
<int name="age" value="4" />
</map>
、、、
 
分析以下几个方法：
一、getSharedPreferences(name,mode)
方法的第一个参数用于指定该文件的名称，名称不用带后缀，后缀会由Android自动加上；
方法的第二个参数指定文件的操作模式，共有四种操作模式。
四种操作模式分别为：
1. MODE_APPEND: 追加方式存储
2. MODE_PRIVATE: 私有方式存储,其他应用无法访问
3. MODE_WORLD_READABLE: 表示当前文件可以被其他应用读取
4. MODE_WORLD_WRITEABLE: 表示当前文件可以被其他应用写入
 
二、edit()方法获取editor对象
Editor editor = sharedPreferences.edit();
editor存储对象采用key-value键值对进行存放，editor.putString("name", "wujaycode");
通过commit()方法提交数据
 
与之对应的获取数据的方法：
SharedPreferences share=getSharedPreferences("Acitivity",Activity.MODE_WORLD_READABLE);

int i=share.getInt("i",0);

String str=share.getString("str","");

boolean flag=share.getBoolean("flag",false);
getString()第二个参数为缺省值，如果preference中不存在该key，将返回缺省值

 
如果你想要删除通过SharedPreferences产生的文件，可以通过以下方法：

File file= new File("/data/data/"+getPackageName().toString()+"/shared_prefs","Activity.xml");

if(file.exists()){

file.delete(); 

Toast.makeText(TestActivity.this, "删除成功", Toast.LENGTH_LONG).show(); }

 
三、访问其他应用中的Preference
如果要访问其他应用中的Preference，必须满足的条件是，要访问的应用的Preference创建时指定了Context.MODE_WORLD_READABLE或者Context.MODE_WORLD_WRITEABLE权限。
举例，假如有个<package name>为com.wujay.action下面的应用使用了下面语句创建了Preference，getSharedPreferences("wujay", Context.MODE_WORLD_READABLE),
现在要访问该Preferences:
首先，需要创建上面的Context,然后通过Context访问Preferences，访问preference时会在应用所在包下的shared_prefs目录找到preference：
Context otherAppsContext = createPackageContext("com.wujay.action", Context.CONTEXT_IGNORE_SECURITY);
SharedPreferences sharedPreferences = otherAppsContext.getSharedPreferences("wujay", Context.MODE_WORLD_READABLE);
String name = sharedPreferences.getString("name", "");
int age = sharedPreferences.getInt("age", 0);
如果不通过创建Context访问其他应用的preference，可以以读取xml文件方式直接访问其他应用preference对应的xml文件，如：
File xmlFile = new File(“/data/data/<package name>/shared_prefs/itcast.xml”);//<package name>应替换成应用的包名。

####
一.保存图片文件

　　首先，将这些数据类型编码成Base64格式，实例化一个ByteArrayOutputStream对象，原来装载压缩后的字节文件。很多人接触ByteArrayOutputStream时不了解，为什么有了FlileOutputStream还需要ByteArrayOutputStream，这就是一个很好的例子。ByteArrayOutputStream用来装载需要缓冲的字节文件，而不当成文件写入磁盘。

　　

　　ByteArrayOutputStream byteArrayOutputStream =new ByteArrayOutputStream();

 　　//然后我们使用BitmapFactory获得我们要压缩的文件，再用compress方法压缩并保存到byteArrayOutputStream。

　　BitmapFactory.decodeResource(getResources(), R.drawable.image1).compress(CompressFormat.JPEG, 50, byteArrayOutputStream);

　　//最后，用Base64.encode将字节文件转换成Base64编码保存在String中。

　　String imageString = new String(Base64.encode(byteArrayOutputStream.toByteArray(),Base64.DEFAULT));

　　byteArrayOutputStream.close();
　　得到图片的String后，我们就可以像上篇文章中一样使用SharedPreferences保存这个数据了。

　　//下面代码将告诉我们如何从文件中读取保存的图片信息。

　　//定义一个byte类型的数组，对Base64格式的字符串进行解码，还原成字节数组。
　　byte[] imageBytes = Base64.decode(string.getBytes(), Base64.DEFAULT);

　　//然后讲imageBytes装载到ByteArrayInputStream。

　　ByteArrayInputStream byteArrayInputStream = new ByteArrayInputStream(imageBytes);

　　//最后，用Drawable的createFromSteam方法将byteArrayInputStream编译成图片文件。　

　　ImageView imageView =(ImageView)findViewById(R.id.imageView1);

　　imageView.setImageDrawable(Drawable.createFromStream(byteArrayInputStream, "image"));

　　byteArrayInputStream.close();

 

　　二.保存对象

　　建立一个类，实例化一个对象

　　public class MobileInfo implements Serializable {
　　//该类实现Serializable接口，以启用其序列化功能
　　private static final long serialVersionUID = 1L;
　　public String name;
　　public String infoString;

　　}

　　MobileInfo mobile = new MobileInfo();

　　mobile.name = "魅族";
　　mobile.infoString = "魅族MX";

　　//和保存图片一样，首先要将数据编码成Base64格式，实例化一个ByteArrayOutputStream对象，原来装载压缩后的字节文件。

　　ByteArrayOutputStream byteArrayOutputStream = new ByteArrayOutputStream();

　　//然后将得到的字符数据装载到ObjectOutputStream。

　　ObjectOutputStream objectOutputStream = new ObjectOutputStream(byteArrayOutputStream);

　　//writeObject 方法负责写入特定类的对象的状态，以便相应的 readObject 方法可以还原它。
　　objectOutputStream.writeObject(mobile);
　　//最后，用Base64.encode将字节文件转换成Base64编码保存在String中
　　String mobilesString = new String(Base64.encode(byteArrayOutputStream.toByteArray(),Base64.DEFAULT));
　　//关闭objectOutputStream
　　objectOutputStream.close();
 


　　//下面代码将告诉我们如何从文件中读取保存的对象,参考图片的读取方法，相信大家能看懂，我就不再解释了
　　byte[] mobileBytes = Base64.decode(mobilesString.getBytes(),Base64.DEFAULT);
　　ByteArrayInputStream byteArrayInputStream = new ByteArrayInputStream(mobileBytes);
　　ObjectInputStream objectInputStream = new ObjectInputStream(byteArrayInputStream);
　　MobileInfo mobileInfo = (MobileInfo) objectInputStream.readObject();
　　objectInputStream.close();

 




1.Drawable—>Bitmap

Resources res=getResources();

Bitmap bmp=BitmapFactory.decodeResource(res, R.drawable.sample_0);
Resources res=getResources();
private byte[] Bitmap2Bytes(Bitmap bm){

2.Bitmap---->Drawable

Drawable drawable =new BitmapDrawable(bmp);



3、Drawable → Bitmap

public static Bitmap drawableToBitmap(Drawable drawable) {

       

        Bitmap bitmap = Bitmap.createBitmap(

                                        drawable.getIntrinsicWidth(),

                                        drawable.getIntrinsicHeight(),

                                        drawable.getOpacity() != PixelFormat.OPAQUE ? Bitmap.Config.ARGB_8888

                                                        : Bitmap.Config.RGB_565);

        Canvas canvas = new Canvas(bitmap);

        //canvas.setBitmap(bitmap);

        drawable.setBounds(0, 0, drawable.getIntrinsicWidth(), drawable.getIntrinsicHeight());

        drawable.draw(canvas);

        return bitmap;

}

4、从资源中获取Bitmap

Bitmap bmp=BitmapFactory.decodeResource(res, R.drawable.pic);

5、Bitmap → byte[]

    ByteArrayOutputStream baos = new ByteArrayOutputStream();

    bm.compress(Bitmap.CompressFormat.PNG, 100, baos);

    return baos.toByteArray();   }

6、 byte[] → Bitmap

   private Bitmap Bytes2Bimap(byte[] b){

                    if(b.length!=0){

                            return BitmapFactory.decodeByteArray(b, 0, b.length);

                    }

                    else {

                            return null;

                    }

          } 