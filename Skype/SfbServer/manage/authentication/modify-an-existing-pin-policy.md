---
title: Modificar una directiva de PIN existente en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: 'Resumen: Modificar una directiva existente de PIN en Skype para Business Server 2015.'
ms.openlocfilehash: bb9be5807da0e72dfbc59d2000af82b181bfc6d6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server-2015"></a>Modificar una directiva de PIN existente en Skype Empresarial Server 2015
 
**Resumen:** Modificar una directiva existente de PIN en Skype para Business Server 2015.
  
Puede utilizar la ficha **Directiva de NIP** para proporcionar autenticación de identificación personal numérica (PIN) a los usuarios que se conectan a Skype para negocios con teléfonos IP. Para usar la autenticación de PIN, asegúrese de que la opción **Habilitar autenticación de PIN** esté seleccionada en la configuración del servicio web.
  
Siga estos pasos para modificar una directiva de PIN de nivel de usuario o de sitio. 
  
### <a name="to-modify-an-existing-pin-policy"></a>Para modificar una directiva de PIN existente

1.  Desde una cuenta de usuario que es miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en el que implementa Skype para Business Server 2015.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.
    
4. En la página **Directiva de PIN**, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
5. En **Editar directiva de PIN**, en **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que desea permitir. La longitud mínima predeterminada es de cinco dígitos.
    
6. Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla   **Especificar número máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.
    
7. Si activa la casilla **Especificar máximo de intentos de inicio de sesión**, en **Número máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.
    
8. Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.
    
9. Si activa la casilla **Habilitar expiración de PIN**, en **El PIN expira tras (días)**, escriba o seleccione el número de días después de los cuales expira el PIN.
    
10. En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar un PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.
    
11. Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, números secuenciales y conjuntos repetitivos de números, active la casilla **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.
    
    > [!IMPORTANT]
    > Se recomienda no permitir patrones comunes. 
  
12. Haga clic en **Confirmar**.
    

