---
title: "Günlük komut penceresinde komut çıktısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: tools.logcommandwindowoutput
helpviewer_keywords:
- log Command window output command
- View.LogCommandWindowOutput command
ms.assetid: d4ecec35-5af4-4954-8d60-2cd24583fbb4
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 21450a0478bb7f2388cdde6b69f6fe661e9a055c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="log-command-window-output-command"></a>Command penceresi çıktısı günlüğü tut komutu
Girdi ve çıktı kopyaları tüm **komutu** bir dosyaya penceresi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Tools.LogCommandWindowOutput [filename] [/on|/off] [/overwrite]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 İsteğe bağlı. Günlük dosyasının adı. Varsayılan olarak, dosyayı kullanıcının profili klasöründe oluşturulur. Dosya adı zaten varsa, günlük varolan dosyanın sonuna eklenir. Hiçbir dosya belirtilirse, belirtilen son dosyası kullanılır. Önceki bir dosya varsa, cmdline.log adlı bir varsayılan günlük dosyası oluşturulur.  
  
> [!TIP]
>  Günlük dosyasının kaydedildiği konumu değiştirmek için yol boşluk içeriyorsa tırnak işaretleri dosyasının tam yolunu girin.  
  
## <a name="switches"></a>Anahtarlar  
 /on  
 İsteğe bağlı. Günlüğü başlatır **komutu** belirtilen dosya penceresinde ve yeni bilgiler ile dosya ekler.  
  
 / Kapalı  
 İsteğe bağlı. Günlüğü durdurur **komutu** penceresi.  
  
 / üzerine yaz  
 İsteğe bağlı. Belirtilen dosya, `filename` bağımsız değişkeni ile eşleşen varolan bir dosyanın, dosyanın üzerine yazılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Hiçbir dosya belirtilirse, dosya cmdline.log varsayılan olarak oluşturulur. Varsayılan olarak, bu komut için diğer ad günlüktür.  
  
## <a name="examples"></a>Örnekler  
 Bu örnekte yeni bir günlük dosyası olan cmdlog, oluşturur ve komut günlük başlatır.  
  
```  
>Tools.LogCommandWindowOutput cmdlog  
```  
  
 Bu örnekte oturum açma komutları durdurur.  
  
```  
>Tools.LogCommandWindowOutput /off  
```  
  
 Bu örnek daha önce kullanılan günlük dosyasında komutları günlüğe sürdürür.  
  
```  
>Tools.LogCommandWindowOutput /on  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio komut diğer adları](../../ide/reference/visual-studio-command-aliases.md)