---
title: "Intellitest başvuru el ile | Microsoft Developer Test Araçları | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IntelliTest Reference Manual, IntelliTest
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 30c23fc51f136d7fc3dcfeca191f5c469fb1e331
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="intellitest-reference-manual"></a>Intellitest başvuru el ile

## <a name="contents"></a>İçindekiler

* **[Intellitest genel bakış](introduction.md)**
  - [Intellitest Merhaba Dünya](introduction.md#hello-world)
  - [Sınırlamalar](introduction.md#limitations)
    * [Nondeterminism](introduction.md#nondeterminism)
    * [Eşzamanlılık](introduction.md#concurrency)
    * [Yerel kod](introduction.md#native-code)
    * [Platform](introduction.md#platform)
    * [Dil](introduction.md#language)
    * [Simgesel mantığı](introduction.md#symbolic-reasoning)
    * [Yanlış Yığın izlemeleri](introduction.md#incorrect-stack)
  - [Daha fazla bilgi](introduction.md#further-reading)<p>&nbsp;</p>

* **[Intellitest ile çalışmaya başlama](getting-started.md)**
  - [Önemli öznitelikleri](getting-started.md#important-attributes)
  - [Önemli statik yardımcı sınıfları](getting-started.md#helper-classes)<p>&nbsp;</p>
 
* **[Test oluşturma](test-generation.md)**
  - [Test oluşturucuları](test-generation.md#test-generators)
  - [Parametreli birim testleri](test-generation.md#parameterized-unit-testing)
  - [Genel parametreli birim testleri](test-generation.md#generic-parameterized)
  - [Özel durumlara izin verme](test-generation.md#allowing-exceptions)
  - [İç türleri test etme](test-generation.md#internal-types)
  - [Varsayımlar ve onaylar](test-generation.md#assumptions-and-assertions)
  - [Önkoşulu](test-generation.md#precondition)
  - [Sonkoşul](test-generation.md#postcondition)
  - [Test başarısızlıklarının](test-generation.md#test-failures)
  - [Kurulum ve kesmeden](test-generation.md#setup-teardown)
  - [Daha fazla bilgi](test-generation.md#further-reading)<p>&nbsp;</p>

* **[Giriş oluşturma](input-generation.md)**
  - [Kısıtlama Çözücü](input-generation.md#constraint-solver)
  - [Dinamik kod kapsamı](input-generation.md#dynamic-code-coverage)
  - [Tamsayılar ve float](input-generation.md#integers-and-floats)
  - [Nesneler](input-generation.md#objects)
  - [Varolan sınıflarını örnekleme](input-generation.md#existing-classes)
  - [Görünürlüğü](input-generation.md#visibility)
  - [Parametreli mocks](input-generation.md#parameterized-mocks)
  - [Yapılar](input-generation.md#structs)
  - [Diziler ve dizeler](input-generation.md#arrays-and-strings)
  - [Ek girişlerini alma](input-generation.md#additional-inputs)
  - [Daha fazla bilgi](input-generation.md#further-reading)<p>&nbsp;</p>

* **[Keşif sınırları](exploration-bounds.md)**
  - [MaxConstraintSolverTime](exploration-bounds.md#maxconstraintsolvertime)
  - [MaxConstraintSolverMemory](exploration-bounds.md#maxconstraintsolvermemory)
  - [MaxBranches](exploration-bounds.md#maxbranches)
  - [MaxCalls](exploration-bounds.md#maxcalls)
  - [MaxStack](exploration-bounds.md#maxstack)
  - [MaxConditions](exploration-bounds.md#maxconditions)
  - [MaxRuns](exploration-bounds.md#maxruns)
  - [MaxRunsWithoutNewTests](exploration-bounds.md#maxrunswithoutnewtests)
  - [MaxRunsWithUniquePaths](exploration-bounds.md#maxrunswithuniquepaths)
  - [MaxExceptions](exploration-bounds.md#maxexceptions)
  - [TestExcludePathBoundsExceeded](exploration-bounds.md#testexcludepathboundsexceeded)
  - [TestEmissionFilter](exploration-bounds.md#testemissionfilter)
  - [TestEmissionBranchHits](exploration-bounds.md#testemissionbranchhits)<p>&nbsp;</p>

* **[Öznitelik sözlüğü](attribute-glossary.md)**
  - [PexAssumeNotNull](attribute-glossary.md#pexassumenotnull)
  - [PexClass](attribute-glossary.md#pexclass)
  - [PexGenericArguments](attribute-glossary.md#pexgenericarguments)
  - [PexMethod](attribute-glossary.md#pexmethod)
  - [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)
  - [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
  - [PexAssemblyUnderTest](attribute-glossary.md#pexassemblyundertest)
  - [PexInstrumentAssemblyAttribute](attribute-glossary.md#pexinstrumentassemblyattribute)
  - [PexUseType](attribute-glossary.md#pexusetype)
  - [PexAllowedException](attribute-glossary.md#pexallowedexception)
  - [PexAllowedExceptionFromAssembly](attribute-glossary.md#pexallowedexceptionfromassembly)
  - [PexAllowedExceptionFromType](attribute-glossary.md#pexallowedexceptionfromtype)
  - [PexAllowedExceptionFromTypeUnderTest](attribute-glossary.md#pexallowedexceptionfromtypeundertest)<p>&nbsp;</p>

* **[Ayarları Waterfall](settings-waterfall.md)**

* **[Statik yardımcı sınıfları](static-helper-classes.md)**
  - [PexAssume](static-helper-classes.md#pexassume)
  - [PexAssert](static-helper-classes.md#pexassert)
  - [PexChoose](static-helper-classes.md#pexchoose)
  - [PexObserve](static-helper-classes.md#pexobserve)
  - [PexSymbolicValue](static-helper-classes.md#pexsymbolicvalue)<p>&nbsp;</p>

* **[Uyarıları ve hataları](warnings-and-errors.md)**
  - [MaxBranches aşıldı](warnings-and-errors.md#maxbranches-exceeded)
  - [MaxConstraintSolverTime aşıldı](warnings-and-errors.md#maxconstraintsolvertime-exceeded)
  - [MaxConditions aşıldı](warnings-and-errors.md#maxconditions-exceeded)
  - [MaxCalls aşıldı](warnings-and-errors.md#maxcalls-exceeded)
  - [MaxStack aşıldı](warnings-and-errors.md#maxstack-exceeded)
  - [MaxRuns aşıldı](warnings-and-errors.md#maxruns-exceeded)
  - [MaxRunsWithoutNewTests aşıldı](warnings-and-errors.md#maxrunswithoutnewtests-exceeded)
  - [Çözüm concretize olamaz](warnings-and-errors.md#cannot-concretize-solution)
  - [Nesnesi oluşturmak için Yardım gerekiyor](warnings-and-errors.md#help-construct)
  - [Türlerini bulmak için Yardım gerekiyor](warnings-and-errors.md#help-types)
  - [Tahmin edilen kullanılabilir türü](warnings-and-errors.md#usable-type-guessed)
  - [Keşif sırasında beklenmeyen hata](warnings-and-errors.md#unexpected-exploration)
  - [TargetInvocationException](warnings-and-errors.md#targetinvocationexception)
  - [Adlı uninstrumented yöntemi](warnings-and-errors.md#uninstrumented-method-called)
  - [Adlı dış yöntemi](warnings-and-errors.md#external-method-called)
  - [Adlı uninstrumentable yöntemi](warnings-and-errors.md#uninstrumentable-method-called)
  - [Test Edilebilirlik sorunu](warnings-and-errors.md#testability-issue)
  - [Sınırlama](warnings-and-errors.md#limitation)
  - [Gözlemlenen çağrısı uyuşmazlığı](warnings-and-errors.md#observed-call-mismatch)
  - [Statik alanda depolanan değer](warnings-and-errors.md#value-static-field)<p>&nbsp;</p>

## <a name="got-feedback"></a>Geri bildirim var mı?

Fikirlerinizi sonrası ve özellik istekleri  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
