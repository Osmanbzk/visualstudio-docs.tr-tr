---
title: CustomParameters öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#CustomParameters
helpviewer_keywords:
- CustomParameters element [Visual Studio project templates]
ms.assetid: cf3efc91-1532-4022-bbb8-a18658424fee
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a4366201e47e6ec682039b5d2a4cd33a8213f7f0
ms.sourcegitcommit: 35bebf794f528d73d82602e096fd97d7b8f82c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/18/2018
ms.locfileid: "53561401"
---
# <a name="customparameters-element-visual-studio-templates"></a>CustomParameters öğesi (Visual Studio şablonları)
Sihirbaz parametresi değişiklik yaptığında için Şablon Sihirbazı'nı geçirilecek özel parametreler gruplandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<CustomParameters>  
    <CustomParameter/>  
    <CustomParameter/>  
</CustomParameters>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt öğeleri  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[CustomParameter](../extensibility/customparameter-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Bir özel parametre adı ve şablondan bir proje veya öğe oluşturulduğunda kullanılacak değeri içerir. Sıfır veya daha fazla olabilir `CustomParameter` öğelerinde bir `CustomParameters` öğesi.|  
  
### <a name="parent-elements"></a>Üst öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Şablonu içeriğini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, şablonda birkaç özel parametreler kullanmayı gösterir. Bir proje veya öğe oluşturulduğunda aşağıdaki özel parametreleri, tüm örneklerini ile bir şablondan `$color1$` ve `$color2$` şablon dosyaları ile değiştirilecek `Red` ve `Blue`sırasıyla.  
  
```  
<CustomParameters>  
    <CustomParameter Name="$color1$" Value="Red"/>  
    <CustomParameter Name="$color2$" Value="Blue "/>  
</CustomParameters>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [CustomParameter öğesi (Visual Studio şablonları)](../extensibility/customparameter-element-visual-studio-templates.md)   
 [Şablon parametreleri](../ide/template-parameters.md)   
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)