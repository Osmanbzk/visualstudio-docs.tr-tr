---
title: "IA64 işlemleri için karışık mod hata ayıklaması desteklenmiyor. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.interop_unsupported_ia64
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 20bc1e38-049b-4388-87c4-936815d85b46
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9965f83feed7d12ac48aefdd248aebfc9a524473
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="mixed-mode-debugging-for-ia64-processes-is-unsupported"></a>IA64 işlemleri için karışık mod hata ayıklaması desteklenmiyor.
Visual Studio IA64 işlemleri yönetilen ve yerel kod karışık mod hata ayıklaması desteklemez. Bu, yerel koda yönetilen koddan ya da yerel koddan yönetilen koda hata ayıklama sırasında adım edilemez olduğunu anlamına gelir.  
  
### <a name="workarounds"></a>Geçici Çözümler  
  
-   Yönetilen ve yerel kod hata ayıklama ayrı hata ayıklama oturumu.  
  
     veya  
  
     Aşağıdaki yordamlarda açıklandığı gibi karma kodunuzu bir 32 bitlik işlem olarak hata ayıklama.  
  
### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>Platform 32-bit (Visual Basic veya C#) değiştirmek için  
  
1.  İçinde **Çözüm Gezgini**, üzerinde projenize sağ tıklayın ve ardından **özellikleri** kısayol menüsünde.  
  
2.  Özellik sayfaları tıklatın **derleme** veya **hata ayıklama** sekmesi.  
  
3.  Tıklatın **Platform** ve x86 platformları listeden seçin.  
  
     Varsayılan olarak, Visual Basic ve C# Derleyicileri varsayılan herhangi bir CPU'da çalıştırmak için kod oluşturur. Bir 64-bit bilgisayarda 64 bit işlemleri olarak bu ikili dosyaları çalıştırın. Bir 32 bitlik işlem olarak çalıştırmak için seçmelisiniz **Win32**değil **AnyCPU**.  
  
### <a name="to-change-the-platform-to-32-bit-cc"></a>Platform 32-bit (C/C++) değiştirmek için  
  
1.  İçinde **Çözüm Gezgini**, üzerinde projenize sağ tıklayın ve ardından **özellikleri** kısayol menüsünde.  
  
2.  Özellik sayfaları tıklatın **Platform** ve Win32 platformları, listeden seçin  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [64 Bit uygulamalarda hata ayıklama](../debugger/debug-64-bit-applications.md)