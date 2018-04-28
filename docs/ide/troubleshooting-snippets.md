---
title: Kod parçacıkları sorunlarını giderme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: troubleshooting
helpviewer_keywords:
- IntelliSense Code Snippets, troubleshooting
- troubleshooting IntelliSense Code Snippets
- troubleshooting Visual Basic, IntelliSense Code Snippets
ms.assetid: 7b6dd40e-2f78-4b50-8e68-41fac1bcb81e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dea93f5c575afc96af188ab2e92e2ee12b929549
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="troubleshoot-snippets"></a>Kod parçacıkları sorunlarını giderme

IntelliSense kod parçacıkları sorunlarını genellikle iki sorunlarından neden: bozuk parçacık dosyasını veya parçacığı dosyasında hatalı içeriği.

## <a name="the-snippet-cannot-be-dragged-from-file-explorer-to-a-visual-studio-source-file"></a>Kod parçacığını dosya Gezgini'nden bir Visual Studio kaynak dosyaya sürüklediğiniz olamaz

-   Kod parçacığında dosyasındaki XML bozulmuş olabilir. **XML Düzenleyicisi** içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sorunları XML yapısı içinde bulabilirsiniz.

-   Parçacık dosyasını parçacığı şemaya uygun olmayabilir. **XML Düzenleyicisi** içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sorunları XML yapısı içinde bulabilirsiniz.

## <a name="the-code-has-compiler-errors-that-are-not-highlighted"></a>Kod değil vurgulanmıştır derleyici hataları var

-   Proje başvurusu eksik olabilir. Kod parçacığını ilgili belgelere inceleyin. Referans bilgisayarda bulunmazsa yüklemeniz gerekir. Parçacık ekleme projeye gerekli tüm başvuruları eklemeniz gerekir. Kod parçacığını başvuru bilgileri eksikse, hata olarak parçacığı oluşturan bildirilebilir.

-   Bir değişken tanımlanmamış olabilir. Tanımsız değişkenlerde parçacık vurgulanmış olması gerekir. Aksi durumda, hata olarak parçacığı oluşturucusu olarak bildirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

- [Kod parçacıkları](../ide/code-snippets.md)
