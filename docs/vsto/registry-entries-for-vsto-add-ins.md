---
title: VSTO eklentileri için kayıt defteri girdileri | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- LoadBehavior entry
- add-ins [Office development in Visual Studio], registry entries
- registry keys [Office development in Visual Studio]
- application-level add-ins [Office development in Visual Studio], registry entries
- registry entries [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 5e4c410a6f934c7b4fe4c6239bdfe07364af3152
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="registry-entries-for-vsto-add-ins"></a>VSTO Eklentileri için Kayıt Defteri Girişleri
  VSTO Visual Studio kullanarak oluşturulan eklentileri dağıttığınızda, belirli bir kayıt defteri girdileri kümesini oluşturmanız gerekir. Bu kayıt defteri girdileri bulmak ve VSTO eklentisi yükleme Microsoft Office uygulama sağlayan bilgiler sağlar.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 Projenizi yapılandırdığınızda, Visual Studio geliştirme bilgisayarınızda bu kayıt defteri girdileri kolayca çalışmasını ve VSTO eklentisi hata ayıklama oluşturur. VSTO eklentinizi dağıtmak için ClickOnce kullanırsanız, kayıt defteri girdileri son kullanıcı bilgisayarda otomatik olarak oluşturulur. VSTO eklentinizi dağıtmak için Windows Installer kullanırsanız, son kullanıcı bilgisayarda kayıt defteri girişleri oluşturmak için InstallShield Limited Edition proje yapılandırmanız gerekir.  
  
 Kayıt defteri girdilerini VSTO eklentileri için yükleme işlemi sırasında nasıl kullanıldığı konusunda daha fazla bilgi için bkz: [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md).  
  
> [!NOTE]  
>  Bu konuda, metin *eklenti kimliği* VSTO eklentinizi için benzersiz bir kimliği temsil eder. Varsayılan olarak, kimlik bilgilerinizi VSTO eklenti derlemesi adıdır.  
  
## <a name="registering-vsto-add-ins-for-the-current-user-vs-all-users"></a>VSTO eklentileri için geçerli kullanıcının vs kaydediliyor. Tüm kullanıcılar  
 Bir VSTO eklentisi yüklü olduğunda, iki yolla kaydedilebilir:  
  
-   Yalnızca geçerli kullanıcı için (diğer bir deyişle, VSTO Eklenti yüklendiğinde o bilgisayara oturum açmış kullanıcıya kullanılabilir). Bu durumda, kayıt defteri girdilerini HKEY_CURRENT_USER altında oluşturulur.  
  
-   Tüm kullanıcılar için (bilgisayarda oturum için VSTO eklentisi kullanabileceğiniz diğer bir deyişle, herhangi bir kullanıcı). Bu durumda, kayıt defteri girdilerini HKEY_LOCAL_MACHINE altında oluşturulur.  
  
 Geçerli kullanıcı için tüm VSTO Visual Studio kullanarak oluşturduğunuz eklentileri kaydedilebilir. Ancak, yalnızca belirli senaryolarda tüm kullanıcılar için VSTO eklentileri kaydedilebilir. Bu senaryolar sürümüne bilgisayarda Microsoft Office ve VSTO eklentisi nasıl dağıtıldığına bağlıdır.  
  
### <a name="microsoft-office-version"></a>Microsoft Office sürümü  
 Office uygulamaları VSTO HKEY_LOCAL_MACHINE veya HKEY_CURRENT_USER altında kayıtlı eklentileri yükleyebilir.  
  
 VSTO HKEY_LOCAL_MACHINE altında kayıtlı Eklentileri yüklemek için bilgisayarlara yüklenen güncelleştirme paketi 976477 olmalıdır. Daha fazla bilgi için bkz. [http://go.microsoft.com/fwlink/?LinkId=184923](http://go.microsoft.com/fwlink/?LinkId=184923).  
  
### <a name="deployment-type"></a>Dağıtım türü  
 Bir VSTO eklentisi dağıtmak için ClickOnce kullanırsanız VSTO eklenti yalnızca geçerli kullanıcı için kaydedilebilir. ClickOnce yalnızca HKEY_CURRENT_USER altında oluşturma anahtarları desteklediğinden budur. VSTO eklenti bir bilgisayardaki tüm kullanıcılara kaydetmek istiyorsanız, VSTO eklenti dağıtmak için Windows Installer kullanmanız gerekir. Bu dağıtım türleri hakkında daha fazla bilgi için bkz: [tarafından ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md) ve [tarafından Windows Installer kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-windows-installer.md).  
  
## <a name="registry-entries"></a>Kayıt defteri girdileri  
 Gerekli VSTO eklenti kayıt defteri girdilerini Visio, dışındaki tüm uygulamalar için aşağıdaki kayıt defteri anahtarı altında bulunan nerede *kök* HKEY_CURRENT_USER veya HKEY_LOCAL_MACHINE.  
  
 **Visio hariç tüm uygulamalar**  
  
|Office sürümü|Yapılandırma yolu|  
|--------------------|------------------------|  
|32 bit:|*Kök*\Software\Microsoft\Office\\*uygulama adı*\Addins\\*eklenti kimliği*|  
|64 bit|*Kök*\Software\Wow6432Node\Microsoft\Office\\*uygulama adı*\Addins\\*eklenti kimliği*|  
  
 **Visio**  
  
|Office sürümü|Yapılandırma yolu|  
|--------------------|------------------------|  
|32 bit:|*Kök*\Software\Microsoft\Visio\Addins\\*eklenti kimliği*|  
|64 bit|*Kök*\Software\Wow6432Node\Visio\Addins\\*eklenti kimliği*|  
  
 Aşağıdaki tabloda, bu kayıt defteri anahtarı altındaki girişleri listeler.  
  
|Giriş|Tür|Değer|  
|-----------|----------|-----------|  
|**Açıklama**|REG_SZ|Gerekli. Kısa bir açıklaması için VSTO eklentisi.<br /><br /> Bu açıklama kullanıcı VSTO eklenti seçtiğinde görüntülenir **eklentileri** bölmesinde **seçenekleri** Microsoft Office uygulamasında iletişim kutusu.|  
|**FriendlyName**|REG_SZ|Gerekli. VSTO görüntülenen eklenti açıklayıcı adını **COM eklentileri** Microsoft Office uygulamasında iletişim kutusu. Varsayılan değer eklenti VSTO kimliğidir.|  
|**LoadBehavior**|REG_DWORD|Gerekli. Uygulama için VSTO eklentisi ve VSTO eklenti (yüklenen ya da kaldırıldığında), geçerli durumunu yüklemeye çalıştığında belirten bir değer.<br /><br /> Varsayılan olarak, bu girdi için VSTO eklentisi başlangıçta yüklendiğini belirten 3'e ayarlanır. Daha fazla bilgi için bkz: [LoadBehavior değerleri](#LoadBehavior). **Not:** bir kullanıcı için VSTO eklentisi devre dışı bırakırsa bu eylemi değiştirir **LoadBehavior** HKEY_CURRENT_USER kayıt defteri kovanında değeri. Değeri, her kullanıcı için **LoadBehavior** HKEY_CURRENT_USER kovanında değerini geçersiz kılar, varsayılan **LoadBehavior** HKEY_LOCAL_MACHINE kovanında tanımlı.|  
|**Bildirimi**|REG_SZ|Gerekli. VSTO eklenti için dağıtım bildirimi tam yolu. Yol, yerel bilgisayardaki bir konuma olabilir bir ağ paylaşımına (UNC) veya bir Web sunucusu (HTTP).<br /><br /> Çözümü dağıtmak için Windows Installer kullanırsanız önek eklemelisiniz **file:///** için **bildirim** yolu. Dize eklemeniz gerekir  **&#124;vstolocal** (diğer bir deyişle, dikey çizgi karakterinden **&#124;** arkasından **vstolocal**) sonuna kadar bu yolu. Bu, çözümünüzün yükleme klasörü, yerine ClickOnce önbelleğine yüklenir sağlar. Daha fazla bilgi için bkz: [tarafından Windows Installer kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-windows-installer.md). **Not:** geliştirme bilgisayarınızda VSTO eklenti derlerken Visual Studio otomatik olarak ekler  **&#124;vstolocal** bu kayıt defteri girişi için bir dize.|  
  
###  <a name="OutlookEntries"></a> Outlook Form bölgeleri için kayıt defteri girişleri  
 Eklentide bir VSTO Outlook için özel form bölgesi oluşturursanız, ek kayıt defteri girdileri form bölgesini Outlook ile kaydetmek için kullanılır. Bu girişler form bölgesini destekleyen her ileti sınıfı için farklı kayıt defteri anahtarı altında oluşturulur. Bu kayıt defteri anahtarlarını aşağıdaki konumda bulunan nerede *kök* HKEY_CURRENT_USER veya HKEY_LOCAL_MACHINE.  
  
 *Kök*\Software\Microsoft\Office\Outlook\FormRegions\\*ileti sınıfı*  
  
 Projenizi yapılandırdığınızda tüm VSTO eklentileri tarafından paylaşılan diğer kayıt defteri girdilerini gibi Visual Studio form bölgesi kayıt defteri girdilerini geliştirme bilgisayarınızda oluşturur. VSTO eklentinizi dağıtmak için ClickOnce kullanırsanız, kayıt defteri girdileri son kullanıcı bilgisayarda otomatik olarak oluşturulur. VSTO eklentinizi dağıtmak için Windows Installer kullanırsanız, son kullanıcı bilgisayarda kayıt defteri girişleri oluşturmak için InstallShield Limited Edition proje yapılandırmanız gerekir.  
  
 Form bölgesi kayıt defteri girdileri hakkında daha fazla bilgi için bkz: [özel biçiminde bir Form Bölgesi konumunu belirtin](http://msdn.microsoft.com/library/office/ff868998.aspx). Outlook form bölgeleri hakkında daha fazla bilgi için bkz: [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).  
  
##  <a name="LoadBehavior"></a> LoadBehavior değerleri  
 **LoadBehavior** altında girdisi *kök*\Software\Microsoft\Office\\*uygulama adı*\Addins\\*eklentisi Kimliği* anahtar için VSTO eklentisi çalışma zamanı davranışını belirtme değerlerin Bitsel bir birleşimi içeriyor. En düşük sıra biti (değerler 0 ile 1) için VSTO eklentisi şu anda kaldırıldı yüklenen mı olduğunu gösterir. Uygulama için VSTO eklentisi yüklemeye çalıştığında diğer BITS gösterir.  
  
 Genellikle, **LoadBehavior** girdisi için 0, 3 veya 16 olarak (ondalık) ayarlamak için tasarlanmıştır olduğunda için VSTO eklentisi son kullanıcı bilgisayarlara yüklenir. Varsayılan olarak, Visual Studio ayarlar **LoadBehavior** VSTO eklentinizi oluşturma veya yayımladığınızda 3 girişi.  
  
 Aşağıdaki tabloda olası tüm değerlerini listeler **LoadBehavior** girişi. Bu tablodaki bazı açıklamalar el ile veya programlama yükleme için VSTO eklentisi bakın. Bir VSTO eklentisini el ile yüklemek için VSTO eklenti yanındaki onay kutusunu seçin **COM eklentileri** iletişim kutusunda uygulama. Bir VSTO eklentisi programlı olarak yüklemek için <xref:Microsoft.Office.Core.COMAddIn.Connect%2A> özelliği <xref:Microsoft.Office.Core.COMAddIn> için VSTO eklentisi temsil eden nesnesi **doğru**.  
  
|Değer (ondalık)|VSTO eklenti durumu|VSTO eklenti yükleme davranışı|Açıklama|  
|--------------------------|-------------------------|--------------------------------|-----------------|  
|0|Kaldırıldı|Otomatik olarak yüklenmez|Uygulama için VSTO eklentisi otomatik olarak yüklemek hiçbir zaman çalışır. Kullanıcı için VSTO eklentisi el ile yüklemek deneyebilir veya VSTO eklenti programlı olarak yüklenebilir.<br /><br /> VSTO eklenti başarıyla yüklendi, **LoadBehavior** değeri 0 olarak kalır, ancak VSTO eklenti durumu **COM eklentileri** iletişim kutusu için VSTO eklentisi yüklü olduğunu belirtmek üzere güncelleştirilir.|  
|1.|Yüklü|Otomatik olarak yüklenmez|Uygulama için VSTO eklentisi otomatik olarak yüklemek hiçbir zaman çalışır. Kullanıcı için VSTO eklentisi el ile yüklemek deneyebilir veya VSTO eklenti programlı olarak yüklenebilir.<br /><br /> Ancak **COM eklentileri** uygulama başladıktan sonra için VSTO eklentisi yüklenir, el ile veya programlama yüklenene kadar VSTO eklenti gerçekte yüklü değil iletişim kutusu gösterir.<br /><br /> Uygulama için VSTO eklentisi, başarılı bir şekilde yüklerse **LoadBehavior** değeri 0 olarak değiştirir ve Uygulama kapandıktan sonra 0'da kalır.|  
|2|Kaldırıldı|Başlangıçta yükle|Uygulama için VSTO eklentisi otomatik olarak yüklemek denemez. Kullanıcı için VSTO eklentisi el ile yüklemek deneyebilir veya VSTO eklenti programlı olarak yüklenebilir.<br /><br /> Uygulama için VSTO eklentisi, başarılı bir şekilde yüklerse **LoadBehavior** değeri 3 olarak değiştirir ve Uygulama kapandıktan sonra 3 kalır.|  
|3|Yüklü|Başlangıçta yükle|Uygulama için VSTO eklentisi uygulama başladığında yüklemeye çalışır. Bu, derlediğinizde veya VSTO eklenti Visual Studio'da yayımlama varsayılan değerdir.<br /><br /> Uygulama için VSTO eklentisi, başarılı bir şekilde yüklerse **LoadBehavior** değeri 3 olarak kalır. VSTO Eklenti yüklenirken bir hata meydana gelirse **LoadBehavior** değer 2'ye değişir ve Uygulama kapandıktan sonra 2 olarak kalır.|  
|8|Kaldırıldı|İsteğe bağlı yükleme|Uygulama için VSTO eklentisi otomatik olarak yüklemek denemez. Kullanıcı için VSTO eklentisi el ile yüklemek deneyebilir veya VSTO eklenti programlı olarak yüklenebilir.<br /><br /> Uygulama için VSTO eklentisi, başarılı bir şekilde yüklerse **LoadBehavior** değeri 9 olarak değişir.|  
|9|Yüklü|İsteğe bağlı yükleme|Uygulama, gerektirdiğinde gibi bir kullanıcı bir kullanıcı Arabirimi öğesi tıkladığında işlevselliği eklentide VSTO (örneğin, özel bir düğmeye Şerit) kullanan için VSTO eklentisi yüklenir.<br /><br /> Uygulama için VSTO eklentisi, başarılı bir şekilde yüklerse **LoadBehavior** değer 9 olarak kalır, ancak VSTO eklenti durumu **COM eklentileri** iletişim kutusu için VSTO eklentisi olduğunu göstermek üzere güncelleştirilir şu anda yüklü. VSTO Eklenti yüklenirken bir hata meydana gelirse **LoadBehavior** değeri 8 olarak değişir.|  
|16|Yüklü|İlk kez yükleyin ve ardından isteğe bağlı yükleme|VSTO isteğe bağlı olarak yüklenmesi eklentinizi istiyorsanız, bu değeri ayarlayın. Kullanıcı uygulamayı ilk kez çalıştırdığında uygulama için VSTO eklentisi yükler. Kullanıcı uygulama çalıştığında uygulama VSTO eklenti tarafından tanımlanan herhangi bir kullanıcı Arabirimi öğeleri yükler, ancak kullanıcı VSTO eklentisi ile ilişkili bir kullanıcı Arabirimi öğesi, kadar için VSTO eklentisi yüklü değil.<br /><br /> Uygulama başarıyla VSTO eklenti ilk kez yüklediğinde **LoadBehavior** VSTO Eklenti yüklenirken değeri 16 olarak kalır. Uygulama kapandıktan sonra **LoadBehavior** değeri 9 olarak değişir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da Office çözümleri mimarisi](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Office çözümleri oluşturma](../vsto/building-office-solutions.md)   
 [Office Çözümünü Dağıtma](../vsto/deploying-an-office-solution.md)  
  
  