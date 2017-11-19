---
title: "Bir ifade değerlendiricisi kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluators, registering
ms.assetid: 236be234-e05f-4ad8-9200-24ce51768ecf
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa0d368a68dcbacc2d8b137011efb5942429b7cc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="registering-an-expression-evaluator"></a>Bir ifade değerlendiricisi kaydetme
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 İfade değerlendirici (EE) kendisi Windows COM ortamı ve Visual Studio ile bir üreteci olarak kaydetmeniz gerekir. Böylece, hata ayıklama altyapısı (DE) adres alanı veya hangi varlık EE başlatır Visual Studio adres alanı eklenemeyebilir bir EE DLL olarak uygulanır.  
  
## <a name="managed-code-expression-evaluator"></a>Yönetilen kod ifade değerlendiricisi  
 EE kendisini genellikle VSIP program için bir çağrı tarafından başlatılan COM ortamıyla kaydeden DLL olan bir sınıf kitaplığı, olarak gerçekleştirilen yönetilen bir kod **regpkg.exe**. COM ortamı için kayıt defteri anahtarları yazılıyor gerçek işlemi otomatik olarak gerçekleştirilir.  
  
 Ana sınıf yöntemi ile işaretlenmiş <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>, bu yöntem DLL com ile kaydedildiğinde çağrılacak olduğunu belirten Genellikle olarak adlandırılan bu kayıt yöntemi `RegisterClass`, Visual Studio ile DLL kaydı görevi gerçekleştirir. Karşılık gelen `UnregisterClass` (ile işaretli <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>), etkilerini alır `RegisterClass` DLL zaman kaldırılır.  
  
 Yönetilmeyen kod içinde yazılmış bir EE için olduğu gibi aynı kayıt defteri girdileri yapılan; tek fark yardımcı bir işlev gibi olmasıdır `SetEEMetric` sizin yerinize yapmaları için. Bu kayıt/silme işleminin örneği şöyle görünür:  
  
### <a name="example"></a>Örnek  
 Bu işlev, yönetilen kod EE nasıl kaydeder ve kendisini Visual Studio ile kaydını siler gösterir.  
  
```csharp  
namespace EEMC  
{  
    [GuidAttribute("462D4A3D-B257-4AEE-97CD-5918C7531757")]  
    public class EEMCClass : IDebugExpressionEvaluator  
    {  
        #region Register and unregister.  
        private static Guid guidMycLang = new Guid("462D4A3E-B257-4AEE-97CD-5918C7531757");  
        private static string languageName = "MyC";  
        private static string eeName = "MyC Expression Evaluator";  
  
        private static Guid guidMicrosoftVendor = new Guid("994B45C4-E6E9-11D2-903F-00C04FA302A1");  
        private static Guid guidCOMPlusOnlyEng = new Guid("449EC4CC-30D2-4032-9256-EE18EB41B62B");  
        private static Guid guidCOMPlusNativeEng = new Guid("92EF0900-2251-11D2-B72E-0000F87572EF");  
  
        /// <summary>  
        /// Register the expression evaluator.  
        /// Set "project properties/configuration properties/build/register for COM interop" to true.  
        /// </summary>  
         [ComRegisterFunctionAttribute]  
        public static void RegisterClass(Type t)  
        {  
            // Get Visual Studio version (set by regpkg.exe)  
            string hive = Environment.GetEnvironmentVariable("EnvSdk_RegKey");  
            string s = @"SOFTWARE\Microsoft\VisualStudio\"  
                        + hive  
                        + @"\AD7Metrics\ExpressionEvaluator";  
  
            RegistryKey rk = Registry.LocalMachine.CreateSubKey(s);  
            if (rk == null)  return;  
  
            rk = rk.CreateSubKey(guidMycLang.ToString("B"));  
            rk = rk.CreateSubKey(guidMicrosoftVendor.ToString("B"));  
            rk.SetValue("CLSID", t.GUID.ToString("B"));  
            rk.SetValue("Language", languageName);  
            rk.SetValue("Name", eeName);  
  
            rk = rk.CreateSubKey("Engine");  
            rk.SetValue("0", guidCOMPlusOnlyEng.ToString("B"));  
            rk.SetValue("1", guidCOMPlusNativeEng.ToString("B"));  
        }  
        /// <summary>  
        /// Unregister the expression evaluator.  
        /// </summary>  
         [ComUnregisterFunctionAttribute]  
        public static void UnregisterClass(Type t)  
        {  
            // Get Visual Studio version (set by regpkg.exe)  
            string hive = Environment.GetEnvironmentVariable("EnvSdk_RegKey");  
            string s = @"SOFTWARE\Microsoft\VisualStudio\"  
                        + hive  
                        + @"\AD7Metrics\ExpressionEvaluator\"  
                        + guidMycLang.ToString("B");  
            RegistryKey key = Registry.LocalMachine.OpenSubKey(s);  
            if (key != null)  
            {  
                key.Close();  
                Registry.LocalMachine.DeleteSubKeyTree(s);  
            }  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code-expression-evaluator"></a>Yönetilmeyen kod ifade değerlendiricisi  
 EE DLL uygulayan `DllRegisterServer` kendisini COM ortamı yanı sıra Visual Studio kaydetmek için işlevi.  
  
> [!NOTE]
>  Örnek kayıt defteri kod MyCEE kod VSIP yükleme EnVSDK\MyCPkgs\MyCEE altında bulunan dosya dllentry.cpp bulunabilir.  
  
### <a name="dll-server-process"></a>DLL sunucu işlemi  
 DLL sunucusu EE kaydederken:  
  
1.  Sınıf üreteci kaydeder `CLSID` normal COM kurallara göre.  
  
2.  Yardımcı işlevini çağırır `SetEEMetric` aşağıdaki tabloda gösterilen EE ölçümleri Visual Studio ile kaydetmek için. İşlev `SetEEMetric` ve aşağıda belirtilen ölçümleri dbgmetric.lib kitaplığı bir parçasıdır. Bkz: [hata ayıklama için SDK Yardımcıları](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) Ayrıntılar için.  
  
    |Ölçüm|Açıklama|  
    |------------|-----------------|  
    |`metricCLSID`|`CLSID`EE sınıf fabrikası|  
    |`metricName`|Görüntülenebilecek bir dize olarak EE adı|  
    |`metricLanguage`|EE dil adını değerlendirmek için tasarlanmış|  
    |`metricEngine`|`GUID`s ile bu EE iş hata ayıklama altyapısını (DE)|  
  
    > [!NOTE]
    >  `metricLanguage``GUID` Dil adı, ancak tarafından tanımlayan olan `guidLang` bağımsız değişkeni `SetEEMetric` dil seçer. Derleyici hata ayıklama bilgileri dosyası oluşturduğunda, uygun yazmalısınız `guidLang` böylece DE kullanmak için hangi EE bilir. DE simgesi sağlayıcısı bu dil için genellikle sorar. `GUID`, hata ayıklama bilgileri dosyasında depolanır.  
  
3.  Visual Studio ile anahtarları HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio altında oluşturarak kaydeder\\*X.Y*, burada *X.Y* ile kaydetmek için Visual Studio sürümü.  
  
### <a name="example"></a>Örnek  
 Bu işlev, nasıl bir yönetilmeyen kod (C++) EE kaydeder ve kendisini Visual Studio ile kaydını siler gösterir.  
  
```cpp  
/*---------------------------------------------------------  
  Registration  
-----------------------------------------------------------*/  
#ifndef LREGKEY_VISUALSTUDIOROOT  
    #define LREGKEY_VISUALSTUDIOROOT L"Software\\Microsoft\\VisualStudio\\8.0"  
#endif  
  
static HRESULT RegisterMetric( bool registerIt )  
{  
    // check where we should register  
    const ULONG cchBuffer = _MAX_PATH;  
    WCHAR wszRegistrationRoot[cchBuffer];  
    DWORD cchFreeBuffer = cchBuffer - 1;  
    wcscpy(wszRegistrationRoot, LREGKEY_VISUALSTUDIOROOT_NOVERSION);  
    wcscat(wszRegistrationRoot, L"\\");  
  
    // this is Environment SDK specific  
    // we check for  EnvSdk_RegKey environment variable to  
    // determine where to register  
    DWORD cchDefRegRoot = lstrlenW(LREGKEY_VISUALSTUDIOROOT_NOVERSION) + 1;  
    cchFreeBuffer = cchFreeBuffer - cchDefRegRoot;  
    DWORD cchEnvVarRead = GetEnvironmentVariableW(  
        /* LPCTSTR */ L"EnvSdk_RegKey", // environment variable name  
        /* LPTSTR  */ &wszRegistrationRoot[cchDefRegRoot],// buffer for variable value  
        /* DWORD   */ cchFreeBuffer);// size of buffer  
    if (cchEnvVarRead >= cchFreeBuffer)  
        return E_UNEXPECTED;  
    // If the environment variable does not exist then we must use   
    // LREGKEY_VISUALSTUDIOROOT which has the version number.  
    if (0 == cchEnvVarRead)  
        wcscpy(wszRegistrationRoot, LREGKEY_VISUALSTUDIOROOT);  
  
    if (registerIt)  
    {  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricCLSID,  
                    CLSID_MycEE,  
                    wszRegistrationRoot );  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricName,  
                    GetString(IDS_INFO_MYCDESCRIPTION),  
                    wszRegistrationRoot );  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricLanguage, L"MyC",  
                    wszRegistrationRoot);  
  
        GUID engineGuids[2];  
        engineGuids[0] = guidCOMPlusOnlyEng;  
        engineGuids[1] = guidCOMPlusNativeEng;  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricEngine,  
                    engineGuids,  
                    2,  
                    wszRegistrationRoot);  
    }  
    else  
    {  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricCLSID,  
                        wszRegistrationRoot);  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricName,  
                        wszRegistrationRoot );  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricLanguage,  
                        wszRegistrationRoot );  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricEngine,  
                        wszRegistrationRoot );  
    }  
  
    return S_OK;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir CLR ifade değerlendiricisi yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [Hata ayıklama için SDK Yardımcıları](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)