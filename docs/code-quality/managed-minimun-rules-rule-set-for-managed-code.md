---
title: Yönetilen kod için yönetilen Minimum kurallar kural kümesi
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 44a50c54-8dd3-42b2-8387-532a150e5a6c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 2ec566fb45b68505849639af00f85bbe81aa6f16
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="managed-minimum-rules-rule-set-for-managed-code"></a>Yönetilen kod için yönetilen Minimum kurallar kural kümesi
En önemli sorunları, kodunuzda olası güvenlik açıklarını, uygulama çökme (Crash) ve diğer önemli mantığı ve tasarım hataları gibi yönetilen Minimum kurallar odaklanır. Projeler için oluşturduğunuz herhangi bir özel kural kümesi içinde bu kural kümesi içermelidir.

|Kural|Açıklama|
|----------|-----------------|
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|Atılabilir alanlara sahip olan türler atılabilir olmalıdır|
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|Boş Sonlandırıcıları kaldırın|
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|Atılabilen alanlar atılmalıdır|
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|ValueType.Equals geçersiz kılma üzerinde eşittir işlecini aşırı yükleme|
