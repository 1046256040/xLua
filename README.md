![](Assets/XLua/Doc/xLua.png)

![](https://img.shields.io/badge/release-v2.1.5-blue.png)

## Unity3D��Lua���֧��

ΪUnity3D����Lua�ű���̵������������ṩ�����߼��������µĿ��ܡ���Ȼ��������ˣ���coco2dx�ϵ�ʵ���������ǣ���LuaΪ�������Ե���Ϸ�ͻ��˱���ǿ��еġ�

* C#��Lua�����໥���öԷ�����API�����ʶԷ��������ݽṹ��
* �༭�����������ɴ��룬������������
* ͬʱ֧��Lua5.3��Luajit2.1��
* Lua������C# delegate��Lua table��C# interface���������䣻
* ���л���ֵ���ͣ�����ö�٣��Լ��ֶ���ֵ���͵�struct����Lua��C#�䴫����C# gc alloc��
* ֧��Lua table��ֵ��C#�������ͣ�
* ���䷽ʽ���Զ���������ã�
* ����Lazyload������
* �ɲ��޸Ĵ�����������Lua��չ��
* ֧������������ο�����
* ����Lua����profiler��
* ֧��������ԣ�

����ϸ�����Խ����뿴[����](Assets/XLua/Doc/features.md)��

## ��װ

ֱ�ӽ�ѹ��Assets�¿��á���һ��ʹ�ý�������Ӱ�Ҳ��װ�����п���Ч����

���ϣ����װ������Ŀ¼���뿴[FAQ](Assets/XLua/Doc/faq.md)��ؽ��ܡ�

## ��������

һ�����������ӽ���3�д��룺

����xLua���ѹ��Unity����AssetsĿ¼�£���һ��MonoBehaviour�ϵ���������Start�������´��룺

```csharp
Lua.LuaEnv luaenv = new XLua.LuaEnv();
luaenv.DoString("CS.UnityEngine.Debug.Log('hello world')");
luaenv.Dispose();
```

1��DoString����Ϊstring������������Ϸ���Lua���룬��ʾ����lua�����C#��UnityEngine.Debug.Log��ӡ�˸���־��

2��һ��LuaEnvʵ����ӦLua����������ڿ����Ŀ��ǣ�����ȫ��Ψһ��

C#��������luaҲ�ܼ򵥣�����Ҫ����lua��ϵͳ�������Ƽ���ʽ�ǣ�

* ����

```csharp
[XLua.CSharpCallLua]
public delegate double LuaMax(double a, double b);
```

* ��

```csharp
var max = luaenv.Global.GetInPath<LuaMax>("math.max");
```

* ����

```csharp
Debug.Log("max:" + max(32, 12));
```

�����һ�Σ��ظ�ʹ�á������˴���Ļ�������max�ǲ�����gc alloc�ġ�

## ����ʾ��:

* [01_Helloworld](Assets/XLua/Examples/01_Helloworld/): �������ŵ����ӡ�
* [02_U3DScripting](Assets/XLua/Examples/02_U3DScripting/): չʾ��ô��lua��дMonoBehaviour��
* [03_UIEvent](Assets/XLua/Examples/03_UIEvent/): չʾ��ô��lua��дUI�߼���
* [04_LuaObjectOrented](Assets/XLua/Examples/04_LuaObjectOrented/): չʾlua��������C#����ϡ�
* [05_NoGc](Assets/XLua/Examples/05_NoGc/): չʾ��ôȥ����ֵ���͵�GC��
* [06_Coroutine](Assets/XLua/Examples/06_Coroutine/): չʾluaЭ����ô��UnityЭ������ϡ�
* [07_AsyncTest](Assets/XLua/Examples/07_AsyncTest/): չʾ��ô��luaЭ�������첽�߼�ͬ������
 
## �ĵ�

* [XLua����.ppt](Assets/XLua/Doc/XLua����.ppt)����������ĵ���
* [XLua�̳�.doc](Assets/XLua/Doc/XLua�̳�.doc)���̳̣������״���[����](Assets/XLua/Tutorial/)��
* [XLua������.doc](Assets/XLua/Doc/XLua������.doc)�������������xLua��
* [XLua����ɾ��������lua��.doc](Assets/XLua/Doc/XLua����ɾ��������lua��.doc)�������ɾ������lua��չ�⡣
* [XLua API.doc](Assets/XLua/Doc/XLua_API.doc)��API�ĵ���

