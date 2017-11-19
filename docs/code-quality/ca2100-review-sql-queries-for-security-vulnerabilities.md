---
title: "CA2100: Gözden SQL sorgularını güvenlik açıkları için | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Review SQL queries for security vulnerabilities
- ReviewSqlQueriesForSecurityVulnerabilities
- CA2100
helpviewer_keywords:
- CA2100
- ReviewSqlQueriesForSecurityVulnerabilities
ms.assetid: 79670604-c02a-448d-9c0e-7ea0120bc5fe
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c28bf4d7162a7b646653ff1833067d47e7ff574d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2100-review-sql-queries-for-security-vulnerabilities"></a>CA2100: SQL sorgularını güvenlik açıkları için gözden geçirin
|||  
|-|-|  
|TypeName|ReviewSqlQueriesForSecurityVulnerabilities|  
|CheckId|CA2100|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir yöntem ayarlar <xref:System.Data.IDbCommand.CommandText%2A?displayProperty=fullName> dize bağımsız değişkeninden yönteme yerleşik bir dize kullanarak özelliği.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, dize değişkeninin kullanıcı girişi içerdiğini varsayar. Kullanıcı girişi ile oluşturulan SQL komut dizesi, SQL enjeksiyon saldırılarına karşı savunmasız durumdadır. Bir SQL ekleme saldırısında, kötü niyetli bir kullanıcının bir sorgu tasarım zarar veya temel alınan veritabanı yetkisiz erişim elde girişimi değiştirir giriş sağlar. Tipik teknikler tek tırnak işareti ya da SQL değişmez değer dize sınırlayıcı kesme işareti ekleme içerir; bir SQL yorum güveninin iki kısa çizgi; ve noktalı virgül yeni bir komut izlediğini belirtir. Kullanıcı girişi sorgu, aşağıdakilerden birini parçası olması gerekiyorsa saldırı riskini azaltmak için sırasına göre verimliliği, listelenen.  
  
-   Saklı yordamı kullanın.  
  
-   Parametreli komut dizesi kullanın.  
  
-   Komut dizesini oluşturmadan önce türü ve içerik için kullanıcı girişi doğrulayın.  
  
 Aşağıdaki [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] türleri uygulayan <xref:System.Data.IDbCommand.CommandText%2A> özelliği veya dize bağımsız değişkeni kullanarak özelliğini ayarlamak oluşturucular sağlayın.  
  
-   <xref:System.Data.Odbc.OdbcCommand?displayProperty=fullName>ve<xref:System.Data.Odbc.OdbcDataAdapter?displayProperty=fullName>  
  
-   <xref:System.Data.OleDb.OleDbCommand?displayProperty=fullName>ve<xref:System.Data.OleDb.OleDbDataAdapter?displayProperty=fullName>  
  
-   <xref:System.Data.OracleClient.OracleCommand?displayProperty=fullName>ve<xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=fullName>  
  
-   [System.Data.SqlServerCe.SqlCeCommand](https://msdn.microsoft.com/library/system.data.sqlserverce.sqlcecommand.aspx) ve [System.Data.SqlServerCe.SqlCeDataAdapter](https://msdn.microsoft.com/library/system.data.sqlserverce.sqlcedataadapter.aspx)  
  
-   <xref:System.Data.SqlClient.SqlCommand?displayProperty=fullName>ve<xref:System.Data.SqlClient.SqlDataAdapter?displayProperty=fullName>  
  
 ToString yöntemi türü açık veya örtülü olarak kullanıldığında, bu kural ihlal fark sorgu dizesi oluşturulamadı. Bir örnek verilmiştir.  
  
```  
int x = 10;  
string query = "SELECT TOP " + x.ToString() + " FROM Table";  
```  
  
 Kötü niyetli bir kullanıcının ToString() yöntemini geçersiz kılabilirsiniz çünkü kural ihlal edildi.  
  
 ToString örtük olarak kullanıldığında, kural ayrıca ihlal edildi.  
  
```  
int x = 10;  
string query = String.Format("SELECT TOP {0} FROM Table", x);  
```  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için parametreli bir sorgu kullanın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Komut metni herhangi bir kullanıcı giriş içermiyorsa, bu kural bir uyarıdan gizlemek güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir yöntemi gösterir `UnsafeQuery`, kural ve bir yöntem ihlal `SaferQuery`, parametreli komut dizesi kullanarak kural karşılayan.  
  
 [!code-vb[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/VisualBasic/ca2100-review-sql-queries-for-security-vulnerabilities_1.vb)]
 [!code-csharp[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CSharp/ca2100-review-sql-queries-for-security-vulnerabilities_1.cs)]
 [!code-cpp[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CPP/ca2100-review-sql-queries-for-security-vulnerabilities_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenlik genel bakış](/dotnet/framework/data/adonet/security-overview)