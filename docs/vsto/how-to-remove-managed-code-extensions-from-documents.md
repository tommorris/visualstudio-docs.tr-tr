---
title: "Nasıl yapılır: belgelerden yönetilen kod uzantılarını kaldırma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- managed code extensions [Office development in Visual Studio], removing
- documents [Office development in Visual Studio], managed code extensions
ms.assetid: e893d9a5-72a5-4087-b81b-04d4d3d9ebf8
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f9da75468ae417bd835b457cdbd5219ef9462df1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-remove-managed-code-extensions-from-documents"></a>Nasıl Yapılır: Belgelerden Yönetilen Kod Uzantılarını Kaldırma
  Bir belge veya Microsoft Office Word veya Microsoft Office Excel için belge düzeyi özelleştirme parçası olan bir çalışma kitabı özelleştirme derlemesini program aracılığıyla kaldırabilirsiniz. Kullanıcılar, ardından belgeleri açın ve içeriğini görüntülemek, ancak belgelere eklediğiniz herhangi bir özel kullanıcı arabirimi (UI) görüntülenmez ve kodunuzu çalışmaz.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Tarafından sağlanan RemoveCustomization yöntemlerden birini kullanarak özelleştirilmiş derlemeyi kaldırabilirsiniz [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Kullandığınız yöntemine bağlıdır, çalışma zamanında özelleştirme kaldırmak istediğiniz (diğer bir deyişle, Word sırasında özelleştirmelerinde kodu çalıştırarak belge veya Excel çalışma kitabı açık değil), ya da kapalı bir belge veya bir belgeden özelleştirme kaldırmak istiyorsanız, i Microsoft Office yüklü olmayan bir sunucuya s.  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [yapmak I: ekleme veya ayırma bir Word belgesi VSTO derlemesinden?](http://go.microsoft.com/fwlink/?LinkId=136782).  
  
### <a name="to-remove-the-customization-assembly-at-run-time"></a>Çalışma zamanında özelleştirme derlemesini kaldırmak için  
  
1.  Özelleştirme kodunuzun çağırması <xref:Microsoft.Office.Tools.Word.Document.RemoveCustomization%2A> yöntemi (için Word) veya <xref:Microsoft.Office.Tools.Excel.Workbook.RemoveCustomization%2A> yöntemi (için Excel). Bu yöntem yalnızca özelleştirme artık gerekli olmadığında çağrılmalıdır.  
  
     Burada, kodunuzda bu yöntemi çağırabilmeniz özelleştirmenizin nasıl kullanıldığına bağlıdır. Örneğin, müşteriler, belgenin kendisine (özelleştirmeye değil) yalnızca gereken diğer istemciler belge göndermek hazır olana kadar sizin özelleştirmenizin özelliklerini kullanıyorsa, müşteri tıklattığında RemoveCustomization çağıran bazı UI sağlayabilirsiniz. İlk açıldığında ama özelleştirme doğrudan müşteriler tarafından erişilen diğer özellikleri sağlamıyor özelleştirmeyi belgeyi verilerle doldurur, alternatif olarak, ardından RemoveCustomization özelleştirme olan en kısa sürede çağırabilirsiniz tamamlandığında belgesi başlatılıyor.  
  
### <a name="to-remove-the-customization-assembly-from-a-closed-document-or-a-document-on-a-server"></a>Kapalı veya bir sunucudaki bir belge özelleştirme derlemesini kaldırmak için  
  
1.  Microsoft Office gibi bir konsol uygulaması gerektirmez proje veya Windows Forms projesi Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll derlemesine başvuru ekleyin.  
  
2.  Aşağıdakileri ekleyin **içeri aktarmalar** veya **kullanarak** kod dosyanın en üstüne deyimi.  
  
     [!code-csharp[Trin_VstcoreDeployment#1](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#1)]
     [!code-vb[Trin_VstcoreDeployment#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#1)]  
  
3.  Statik çağrısı <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A> yöntemi <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> sınıfı ve parametresi için çözüm belgesi konumunu belirtin.  
  
     Aşağıdaki kod örneğinde adlandırılmış bir belgeden özelleştirmeyi kaldırdığınızı varsayar **WordDocument1.docx** masaüstünde olmasıdır.  
  
     [!code-csharp[Trin_VstcoreDeployment#2](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#2)]
     [!code-vb[Trin_VstcoreDeployment#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#2)]  
  
4.  Projeyi oluşturun ve uygulamayı özelleştirme kaldırmak istediğiniz bilgisayarda çalıştırın. Bilgisayar Office yüklü çalışma zamanı için Visual Studio 2010 Araçları olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ServerDocument sınıfını kullanarak bir sunucu üzerinde belgeleri yönetme](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [Nasıl yapılır: belgelere yönetilen kod uzantıları ekleme](../vsto/how-to-attach-managed-code-extensions-to-documents.md)  
  
  