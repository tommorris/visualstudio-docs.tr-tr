---
title: Birden çok işlemciye duyarlı Günlükçüler yazılıyor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- msbuild, multi-proc aware loggers
- multi-proc loggers
- loggers, multi-proc
ms.assetid: ff987d1b-1798-4803-9ef6-cc8fcc263516
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2a01fb5d47f390c311f119e669e7fdb75619b058
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31572601"
---
# <a name="writing-multi-processor-aware-loggers"></a>Birden Çok İşlemciye Duyarlı Günlükçüler Yazılıyor
Özelliğini [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] birden çok işlemci yararlanmak için zaman derleme projesi düşmesine neden olur, ancak aynı zamanda olay günlüğü oluşturmak için karmaşıklık ekler. Bir tek işlemcili ortamda olayları, iletilerini, uyarıları ve hataları tahmin edilebilir ve sıralı bir şekilde Günlükçü ulaşır. Ancak, birden çok işlemcili ortamda farklı kaynaklardan gelen olayların aynı anda veya sıra dışı ulaşır. Bunun için sağlamak için [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] çok işlemciye duyarlı Günlükçü ve yeni bir günlük modeli sağlar ve özel "iletme günlükçüleri." oluşturmanıza olanak tanır  
  
## <a name="multi-processor-logging-challenges"></a>Birden çok işlemcili günlük zorlukları  
 Birden çok işlemcili veya çok çekirdekli bir sistemde bir veya daha fazla projeler derlerken [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] tüm projeleri aynı anda oluşturulan için derleme olayları. Aynı anda veya sıra dışı bir avalanche olay iletileri Günlükçü gelebilir. Çünkü bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 2.0 Günlükçü bu durumu işlemek üzere tasarlanmamıştır, Günlükçü doldurmaya ve artan derleme sürelerini, yanlış Günlükçü çıkış veya bozuk bir yapı neden. Bu adres sorunlarını için Günlükçü (başlayarak [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5) dizisi olayları işlemek ve bağıntılı olaylar ve kaynakları kullanabilirsiniz.  
  
 Özel iletme Günlükçü oluşturarak daha fazla günlük verimliliğini artırabilir. Özel iletme Günlükçü izin vererek, bir filtre işlevi görür seçin, oluşturmadan önce izlemek istediğiniz olayları. Özel iletme Günlükçü kullandığınızda, istenmeyen olayları, Günlükçü doldurmaya, günlüklerinizi karmaşıklığa veya yavaş kez derleme olamaz.  
  
## <a name="multi-processor-logging-models"></a>Birden çok işlemcili günlük modelleri  
 Derleme çok-işlemciye ile ilgili sorunlar için sağlamak için [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] iki günlük modeli, merkezi ve dağıtılmış destekler.  
  
### <a name="central-logging-model"></a>Merkezi günlük kaydı modeli  
 Merkezi günlük kaydı modelindeki MSBuild.exe tek bir örneğini "merkezi düğümü" görev yapar ve bu derleme görevleri yardımcı olmak için merkezi düğümü merkezi düğümü ("ikincil düğümler") alt örneklerini ekleyin.  
  
 ![Merkezi Günlükçü modeli](../msbuild/media/centralnode.png "CentralNode")  
  
 Günlükçüleri merkezi düğümüne ekleme çeşitli türlerdeki "merkezi günlükçüleri." bilinen Her Günlükçü türünün yalnızca bir örneği aynı anda merkezi düğüme eklenebilir.  
  
 Bir yapı ortaya çıktığında, ikincil düğümü bunların derleme olaylarını merkezi düğüme rota. Merkezi düğümü, bir veya daha fazla ekli merkezi günlükçüleri tüm olayları ve ayrıca bu ikincil düğümlerinin yönlendirir. Günlükçüleri ardından gelen verileri temel alan günlük dosyaları oluşturun.  
  
 Yalnızca rağmen <xref:Microsoft.Build.Framework.ILogger> olduğu merkezi Günlükçü tarafından uygulanması için gereken, aynı zamanda uygulama öneririz <xref:Microsoft.Build.Framework.INodeLogger> böylece merkezi Günlükçü yapı katılan düğüm sayısı ile başlatır. Aşağıdaki aşırı yükleme <xref:Microsoft.Build.Framework.ILogger.Initialize%2A> Günlükçü altyapısını başlatır, yöntemini çağırır.  
  
```csharp
public interface INodeLogger: ILogger  
{  
    public void Initialize(IEventSource eventSource, int nodeCount);  
}  
```  
  
 Var olan önceden <xref:Microsoft.Build.Framework.ILogger>-tabanlı günlükçüleri merkezi günlükçüleri davranıp ve yapı ekleyebilirsiniz. Ancak, birden çok işlemcili günlük kaydı senaryoları ve sipariş olayları açık desteği olmadan yazılan merkezi günlükçüleri derleme bölün veya anlamsız bir çıktı oluşturmak.  
  
### <a name="distributed-logging-model"></a>Dağıtılmış günlük modeli  
 Aynı anda çok sayıda proje oluşturma sırasında Merkezi günlük kaydı modelinde, çok fazla gelen ileti trafiği merkezi düğümü, örneğin, yük getirebilir. Bu, sistem kaynaklarını stres ve yapı performansını düşürebilir. Bu sorunu kolaylaştırmak için [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] dağıtılmış günlük modelini destekler.  
  
 ![Dağıtılmış günlük modeli](../msbuild/media/distnode.png "DistNode")  
  
 Dağıtılmış günlük modeli, bir iletme Kaydedici oluşturmanıza izin vererek Merkezi günlük kaydı modelini genişletir.  
  
#### <a name="forwarding-loggers"></a>İletme Günlükçüleri  
 Bir iletme Kaydedici ikincil düğüme ekler ve bu düğümden gelen derleme olaylarını alan olay filtresi sahip ikincil ve basit bir Günlükçü ' dir. Gelen olayları filtreler ve merkezi düğüme belirttiğiniz olanları iletir. Bu merkezi düğüme gönderilmiş olan ve genel derleme performansı iyileştirir ileti trafiğini azaltır.  
  
 Dağıtılmış, aşağıdaki gibi oturum kullanmanın iki yolu vardır:  
  
-   Adlı önceden üretilmiş iletme Günlükçü özelleştirme <xref:Microsoft.Build.BuildEngine.ConfigurableForwardingLogger>.  
  
-   Kendi özel iletme Günlükçü yazma.  
  
 ConfigurableForwardingLogger gereksinimlerinize uyacak şekilde değiştirebilirsiniz. Bunu yapmak için MSBuild.exe kullanarak, komut satırında Günlükçü aramak ve Günlükçü merkezi düğüme iletmek istediğiniz yapı olayları listele.  
  
 Alternatif olarak, bir özel iletme Kaydedici oluşturabilirsiniz. Özel iletme Günlükçü oluşturarak Günlükçü davranışını ince ayar yapabilirsiniz. Ancak, özel iletme Günlükçü oluşturma yalnızca ConfigurableForwardingLogger özelleştirme değerinden daha karmaşıktır. Daha fazla bilgi için bkz: [iletme Günlükçüleri oluşturma](../msbuild/creating-forwarding-loggers.md).  
  
## <a name="using-the-configurableforwardinglogger-for-simple-distributed-logging"></a>Günlüğe kaydetme için basit ConfigurableForwardingLogger kullanarak dağıtılmış  
 Bir ConfigurableForwardingLogger veya özel iletme Günlükçü eklemek için kullanın `/distributedlogger` geçiş (`/dl` kısaca) MSBuild.exe komut satırı derleme içinde. Günlükçü türleri ve sınıf adları belirtmek için biçimi için aynıdır `/logger` dağıtılmış Günlükçü her zaman bir iletme Günlükçü ve merkezi Günlükçü yerine iki günlük sınıf olan geçin. XMLForwardingLogger adlı bir özel iletme Kaydedici ekleme konusunda bir örnek verilmiştir.  
  
```  
msbuild.exe myproj.proj/distributedlogger:XMLCentralLogger,MyLogger,Version=1.0.2,Culture=neutral*XMLForwardingLogger,MyLogger,Version=1.0.2,Culture=neutral  
```  
  
> [!NOTE]
>  Bir yıldız işareti (*) iki Günlükçü adlarında ayırmalısınız `/dl` geçin.  
  
 ConfigurableForwardingLogger kullanmaktır diğer Günlükçü kullanarak gibi (kısmında özetlendiği gibi [yapı günlükleri alma](../msbuild/obtaining-build-logs-with-msbuild.md)), tipik yerine ConfigurableForwardingLogger Günlükçü ekleme dışında [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Günlükçü ve parametre olarak merkezi düğüme geçmesine ConfigurableForwardingLogger istediğiniz olayları belirtin.  
  
 Örneğin, yalnızca bir yapı başlar ve biter ve bir hata oluştuğunda bildirim almak istiyorsanız, geçip geçmeyeceğini `BUILDSTARTEDEVENT`, `BUILDFINISHEDEVENT`, ve `ERROREVENT` parametre olarak. Noktalı virgülle ayrılarak birden çok parametre geçirilebilir. Aşağıdaki ConfigurableForwardingLogger yalnızca iletmek için nasıl kullanılacağını örneğidir `BUILDSTARTEDEVENT`, `BUILDFINISHEDEVENT`, ve `ERROREVENT` olaylar.  
  
```  
msbuild.exe myproj.proj /distributedlogger:XMLCentralLogger,MyLogger,Version=1.0.2,Culture=neutral*ConfigureableForwardingLogger,C:\My.dll;BUILDSTARTEDEVENT; BUILDFINISHEDEVENT;ERROREVENT  
```  
  
 Kullanılabilir ConfigurableForwardingLogger parametrelerin bir listesi verilmiştir.  
  
|ConfigurableForwardingLogger parametreleri|  
|---------------------------------------------|  
|BUILDSTARTEDEVENT|  
|BUILDFINISHEDEVENT|  
|PROJECTSTARTEDEVENT|  
|PROJECTFINISHEDEVENT|  
|TARGETSTARTEDEVENT|  
|TARGETFINISHEDEVENT|  
|TASKSTARTEDEVENT|  
|TASKFINISHEDEVENT|  
|ERROREVENT|  
|WARNINGEVENT|  
|HIGHMESSAGEEVENT|  
|NORMALMESSAGEEVENT|  
|LOWMESSAGEEVENT|  
|CUSTOMEVENT|  
|KOMUT SATIRI|  
|PERFORMANCESUMMARY|  
|NOSUMMARY|  
|SHOWCOMMANDLINE|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletme Günlükçüleri Oluşturma](../msbuild/creating-forwarding-loggers.md)