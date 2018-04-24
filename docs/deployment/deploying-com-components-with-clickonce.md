---
title: ClickOnce ile COM bileşenleri dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- registration-free COM deployment
- ClickOnce deployment, COM components
- COM components, deploying
- deploying applications [ClickOnce], COM components
- components, deploying
ms.assetid: 1a4c7f4c-7a41-45f2-9af4-8b1666469b89
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 740d72f0ec339ded8ec8b721bbc2b94d706f8da7
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="deploying-com-components-with-clickonce"></a>ClickOnce ile COM Bileşenleri Dağıtma
Eski COM bileşenlerini dağıtımını geleneksel zor bir görev olmuştur. Bileşenleri Genel kayıtlı olması gerekir ve bu nedenle örtüşen uygulamalar arasında istenmeyen yan etkileri neden olabilir. Bileşenler bir uygulama için tamamen yalıtılmış veya yan yana uyumlu değildir çünkü bu durum genelde .NET Framework uygulamalarında bir sorun değildir. Visual Studio yalıtılmış COM bileşenleri Windows XP veya daha yüksek işletim sistemi dağıtmanıza olanak tanır.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] .NET uygulamaları dağıtmak için kolay ve güvenli bir mekanizma sağlar. Ancak, uygulamalarınızı eski COM bileşenleri kullanıyorsanız, bunları dağıtmak için ek adımlar uygulamanız gerekir. Bu konu, yalıtılmış COM bileşenlerini dağıtmak ve yerel bileşenleri (örneğin, Visual Basic 6.0 veya Visual C++) başvuru açıklar.  
  
 Yalıtılmış COM bileşenleri dağıtma hakkında daha fazla bilgi için bkz: "basitleştirin uygulama dağıtımı ile [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ve Kayıtsız COM" konumundaki [ http://msdn.microsoft.com/msdnmag/issues/05/04/RegFreeCOM/default.aspx ](http://msdn.microsoft.com/msdnmag/issues/05/04/RegFreeCOM/default.aspx).  
  
## <a name="registration-free-com"></a>Kayıtsız COM  
 Kayıtsız COM dağıtımı ve yalıtılmış COM bileşenlerini etkinleştirme için yeni bir teknolojidir. Bileşenin tüm tür kitaplığı ve genellikle bir bildirim adlı bir XML dosyasına sistem kayıt defterine yüklenir kayıt bilgileri koyarak çalıştığı uygulama ile aynı klasörde depolanır.  
  
 Bir COM bileşeni yalıtma geliştiricinin makinesinde kayıtlı olması gerekir, ancak son kullanıcının bilgisayarda kayıtlı olması gerekmez. Bir COM bileşeni ayırmak için tüm yapmanız gereken ayarlanmış bunun referansının **Isolated** özelliğine **doğru**. Varsayılan olarak, bu özelliği ayarlamak **yanlış**, kayıtlı COM referansı olarak değerlendirilmesi gerektiğini belirten. Bu özellik ise **doğru**, derleme zamanında bu bileşen için oluşturulacak bir bildirime neden olur. Yükleme sırasında uygulama klasörüne kopyalanmasını karşılık gelen dosyalar neden olur.  
  
 Bildirim oluşturucu ayrılmış bir COM başvurusuna karşılaştığında, tüm numaralandırır `CoClass` girişleri her giriş karşılık gelen kayıt verilerini ile eşleşen ve oluşturma bileşenin türü Kitaplığı ' nda tüm COM tanımlarında bildirimi tür kitaplığı dosyasında sınıflar.  
  
## <a name="deploying-registration-free-com-components-using-clickonce"></a>ClickOnce kullanarak Kayıtsız COM bileşenleri dağıtma  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] çünkü dağıtım teknolojisi yalıtılmış COM bileşenlerini dağıtmak için oldukça uygun her ikisi de [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ve Kayıtsız COM gerekli bir bileşen dağıtılması için bir bildirime sahip.  
  
 Genellikle, bileşenin yazarı bir bildirim sağlamalıdır. Aksi durumda, ancak, Visual Studio bir bildirim otomatik olarak bir COM bileşeni oluşturma yeteneğine sahiptir. Bildirim oluşturulması sırasında gerçekleştirilen [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] işlem yayımlama; daha fazla bilgi için bkz: [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md). Bu özellik ayrıca, Visual Basic 6.0 gibi önceki geliştirme ortamlarında yazılmış eski bileşenleri yararlanmanızı sağlar.  
  
 İki yolla, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] COM bileşenlerini dağıtır:  
  
-   COM bileşenlerini dağıtmak için önyükleyici kullanın; Bu, tüm desteklenen platformlarda çalışır.  
  
-   Yerel bileşen yalıtımı (olarak da bilinen Kayıtsız COM) dağıtımını kullanın. Ancak, bu yalnızca bir Windows XP veya daha yüksek işletim sistemi üzerinde çalışır.  
  
### <a name="example-of-isolating-and-deploying-a-simple-com-component"></a>Örneği yalıtarak ve basit bir COM bileşeni dağıtma  
 Kayıtsız COM bileşeni dağıtımı göstermek için bu örnek Windows tabanlı bir uygulama, Visual Basic 6.0 kullanılarak oluşturulan bir yalıtılmış yerel COM bileşeni başvuran Visual Basic oluşturur ve kullanarak dağıtmak [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  
  
 İlk yerel COM bileşeni oluşturmanız gerekir:  
  
##### <a name="to-create-a-native-com-component"></a>Yerel bir COM bileşeni oluşturmak için  
  
1.  Visual Basic 6.0 kullanan **dosya** menüsünde tıklatın **yeni**, ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **Visual Basic** düğümü ve select bir **ActiveX DLL** projesi. İçinde **adı** kutusuna `VB6Hello`.  
  
    > [!NOTE]
    >  Kayıtsız COM ile yalnızca ActiveX DLL ve ActiveX denetimi proje türleri desteklenir; ActiveX EXE ve ActiveX Document proje türleri desteklenmez.  
  
3.  İçinde **Çözüm Gezgini**, çift **Class1.vb'ye** Metin Düzenleyicisi'ni açın.  
  
4.  Class1.vb içinde için oluşturulan koddan sonra aşağıdaki kodu ekleyin `New` yöntemi:  
  
    ```  
    Public Sub SayHello()  
       MsgBox "Message from the VB6Hello COM component"  
    End Sub  
    ```  
  
5.  Bileşeni oluşturun. Gelen **yapı** menüsünde tıklatın **yapı çözümü**.  
  
> [!NOTE]
>  Kayıtsız COM yalnızca DLL'leri destekler ve proje türleri COM denetler. Kayıtsız COM exe kullanamazsınız  
  
 Artık Windows tabanlı bir uygulama oluşturun ve COM bileşenine bir başvuru ekleyin.  
  
##### <a name="to-create-a-windows-based-application-using-a-com-component"></a>Bir COM bileşeni kullanarak Windows tabanlı bir uygulama oluşturmak için  
  
1.  Visual Basic kullanan **dosya** menüsünde tıklatın **yeni**, ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **Visual Basic** düğümü ve select **Windows uygulaması**. İçinde **adı** kutusuna `RegFreeComDemo`.  
  
3.  İçinde **Çözüm Gezgini**, tıklatın **tüm dosyaları göster** düğmesini proje başvurularını görüntülemek için.  
  
4.  Sağ **başvuruları** düğümü ve select **Başvuru Ekle** ve bağlam menüsünden.  
  
5.  İçinde **Başvuru Ekle** iletişim kutusu, tıklatın **Gözat** sekmesinde, VB6Hello.dll'e gidin ve ardından seçin.  
  
     A **VB6Hello** başvuru başvuruları listede görünür.  
  
6.  İşaret **araç**seçin bir **düğmesini** denetlemek ve sürükleyin **Form1** formu.  
  
7.  İçinde **özellikleri** penceresindeki ayarlayın düğmenin **metin** özelliğine **Hello**.  
  
8.  İşleyici kod eklemek için düğmesini çift tıklayın ve böylece işleyici aşağıdaki gibidir kod dosyasında kodu ekleyin:  
  
    ```  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
        Dim VbObj As New VB6Hello.Class1  
        VbObj.SayHello()  
    End Sub  
    ```  
  
9. Uygulamayı çalıştırın. Gelen **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat**.  
  
 Sonraki denetimi ayırmanız gerekir. Uygulamanızın kullandığı her bir COM bileşeni projenizde COM başvuru olarak temsil edilir. Bu başvuruları altında görünür **başvuruları** düğümünde **Çözüm Gezgini** penceresi. (Ekleyebilirsiniz bildirim başvuran ya da kullanarak doğrudan **Başvuru Ekle** komutunu **proje** menüsünde veya dolaylı bir ActiveX denetimini formunuza sürükleyerek.)  
  
 Aşağıdaki adımlar, COM bileşeninin yalıtmak ve ayrılmış denetimi içeren güncelleştirilmiş bir uygulama yayımlama gösterir:  
  
##### <a name="to-isolate-a-com-component"></a>Bir COM bileşeni ayırmak için  
  
1.  İçinde **Çözüm Gezgini**, **başvuruları** düğümü, select **VB6Hello** başvuru.  
  
2.  İçinde **özellikleri** penceresinde değerini değiştirme **Isolated** özelliğinden **False** için **doğru**.  
  
3.  Gelen **yapı** menüsünde tıklatın **yapı çözümü**.  
  
 Şimdi, ne zaman beklendiği gibi uygulama works F5 tuşuna basın, ancak şimdi kayıtsız COM altında çalışıyor. Bu, kanıtlamak için VB6Hello.dll bileşen kaydını ve Visual Studio IDE dışında RegFreeComDemo1.exe çalıştıran deneyin. Düğme tıklatıldığında, bu kez hala çalışır. Uygulama bildirimini geçici olarak yeniden adlandırın, yeniden başarısız olur.  
  
> [!NOTE]
>  Geçici olarak kaydını kaldırarak bir COM bileşeni yokluğu benzetimini yapabilirsiniz. Bir komut istemi açın, yazarak sistem klasörünüze gidin `cd /d %windir%\system32`, ardından yazarak bileşeninin kaydı `regsvr32 /u VB6Hello.dll`. Bunu yeniden yazarak kaydedebilirsiniz `regsvr32 VB6Hello.dll`.  
  
 Kullanarak uygulamayı yayımlamak için son adımdır [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]:  
  
##### <a name="to-publish-an-application-update-with-an-isolated-com-component"></a>Yalıtılmış bir COM bileşeni ile bir uygulama güncelleştirmesi yayımlamak için  
  
1.  Gelen **yapı** menüsünde tıklatın **yayımlama RegFreeComDemo**.  
  
     Yayımlama Sihirbazı görünür.  
  
2.  Yayımlama Sihirbazı'nda, burada erişmek ve yayımlanan dosyalarını inceleyin yerel bilgisayarın diskte bir konum belirtin.  
  
3.  Tıklatın **son** uygulamayı yayımlamak için.  
  
 Yayımlanmış dosyaları incelerseniz, sysmon.ocx dosyasının dahil olduğunu unutmayın. Son kullanıcının makinede denetiminin farklı bir sürümü kullanılarak başka bir uygulama varsa, onu bu uygulamayla müdahale edemez olduğunu anlamına gelir, bu uygulama için tamamen yalıtılmış denetimdir.  
  
## <a name="referencing-native-assemblies"></a>Yerel derlemelere başvurma  
 Visual Studio yerel Visual Basic 6.0 veya C++ derleme başvurularını destekler; Bu tür başvuruları yerel başvuru adı verilir. Bir başvuru olduğunu doğrulayarak yerel mi olduğunu anlayabilirsiniz kendi **dosya türü** özelliği ayarlanmış **yerel** veya **ActiveX**.  
  
 Yerel bir başvuru eklemek için kullanın **Başvuru Ekle** komutu sonra bildirime göz atın. Bazı bileşenler bildirimi DLL içine koyun. Bu durumda, DLL seçmeniz yeterlidir ve Visual Studio bileşen gömülü bir bildirim içeren algılarsa, yerel bir başvuru olarak ekleyecektir. Visual Studio, herhangi bir bağımlı dosyaları veya başvurulan bileşeni ile aynı klasörde bulunmaları durumunda bildiriminde listelenen derlemeleri da otomatik olarak dahil edilir.  
  
 COM denetimi yalıtım bildirimleri henüz COM bileşenlerini dağıtmak kolaylaştırır. Ancak, bir bileşen bir bildirimle sağlanırsa, bildirime doğrudan başvurabilirsiniz. Aslında, her zaman mümkün olduğunda kullanarak yerine bileşen yazarı tarafından sağlanan bildirimi kullanmalısınız **Isolated** özelliği.  
  
## <a name="limitations-of-registration-free-com-component-deployment"></a>Kayıtsız COM bileşeni dağıtımı sınırlamaları  
 Kayıtsız COM geleneksel dağıtım teknikleri Temizle avantaj sağlar. Ancak, bazı sınırlamalar ve ayrıca işaret edilmesi gereken uyarılar vardır. En büyük sınırlama, yalnızca Windows XP veya üzeri çalışmasıdır. Kayıtsız COM uygulama bileşenleri çekirdek işletim sistemi yüklenen şekilde değişiklikler gerekmiştir. Ne yazık ki, hiçbir alt düzey destek katmanı Kayıtsız COM için yok  
  
 Her bileşen Kayıtsız COM uygun adaydır Aşağıdakilerden biri doğruysa bir bileşen uygun bir değil:  
  
-   Bileşen bir işlem dışı sunucusudur. EXE sunucular desteklenmez; yalnızca DLL'ler desteklenir.  
  
-   Bileşen işletim sisteminin bir parçası olduğundan veya XML, Internet Explorer veya Microsoft Data Access Components (MDAC) gibi bir sistem bileşeni. Yeniden dağıtım ilkesi bileşen yazarının izlemelidir; satıcınızla birlikte denetleyin.  
  
-   Microsoft Office gibi bir uygulamanın parçası bileşenidir. Örneğin, Microsoft Excel nesne modeline yalıtmak çalışmamalısınız. Bu, Office bir parçasıdır ve yalnızca tam Office ürünü yüklü bir bilgisayarda kullanılabilir.  
  
-   Bileşen bir eklenti veya bir ek bileşeni, örneğin bir Office Eklentisi veya bir Web tarayıcısında bir denetim olarak kullanıma yöneliktir. Bu bileşenler genellikle kayıt düzeni bildirimi kapsamı dışındadır barındırma ortamı tarafından tanımlanan bir tür gerektirir.  
  
-   Bileşen sistemi, örneğin, yazdırma biriktiricisi bir aygıt sürücüsü için fiziksel veya sanal bir cihaz yönetir.  
  
-   Veri erişim redistributable bileşendir. Veri uygulamaları genellikle ayrı veri çalıştırılmadan önce yüklenecek erişim redistributable gerektirir. Microsoft ADO veri denetimi, Microsoft OLE DB veya Microsoft Data Access Components (MDAC) gibi bileşenleri ayırmaya çalışmamalısınız. Bunun yerine, uygulamanız MDAC veya SQL Server Express kullanıyorsa, bunları önkoşul olarak ayarlamalısınız; bkz: [nasıl yapılır: ClickOnce uygulamasına Önkoşullar yükleme](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md).  
  
 Bazı durumlarda bileşen geliştiricisi Kayıtsız COM için yeniden tasarlayabilir mümkün olabilir Bu mümkün değilse, hala oluşturun ve bunlara önyükleyici kullanarak standart kayıt düzeni bağımlı uygulamaları yayımlama. Daha fazla bilgi için bkz: [önyükleyici paketleri oluşturma](../deployment/creating-bootstrapper-packages.md).  
  
 Bir COM bileşeni yalnızca uygulama başına bir kez ayrılmış olabilir. Örneğin, iki farklı aynı COM bileşeni ayıramazsınız **sınıf kitaplığı** aynı uygulamanın parçası olan projeleri. Uygulamanın çalışma zamanında yüklenmesi başarısız olur ve bunun yapılması bir yapı uyarısına neden olur. Bu sorunu önlemek için Microsoft, COM bileşenleri tek Sınıf Kitaplığı'nda kapsülleyen önerir.  
  
 Uygulama dağıtımının kayıt gerektirmez olsa bile COM geliştiricinin makinesinde kayıt gereken birkaç senaryo vardır. `Isolated` Özelliği gerektirir otomatik-bildirim sırasında yapı oluşturmak için COM bileşeninin geliştiricinin makinesinde kayıtlı olmalıdır. Derleme sırasında kendi kendine kayıt çağıran kayıt yakalama özelliği yoktur. Ayrıca, açıkça Tür Kitaplığı'nda tanımlanan sınıflar bildiriminde yansıtılmaz. Bir COM bileşeni yerel bir referans gibi önceden varolan bir bildirim ile kullanırken Bileşen geliştirme anında kaydedilecek gerekmeyebilir. Ancak, kayıt bir ActiveX denetimini bileşenidir ve olmasını istiyorsanız gereklidir **araç** ve Windows Forms Tasarımcısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Güvenliği ve Dağıtımı](../deployment/clickonce-security-and-deployment.md)