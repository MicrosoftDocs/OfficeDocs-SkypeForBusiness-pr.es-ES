---
title: Modificar una directiva de PIN existente en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: 'Resumen: modifique una directiva de PIN existente en Skype Empresarial Server.'
ms.openlocfilehash: dac6540407ed019fe9147d86bc119426a6679574
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754873"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a>Modificar una directiva de PIN existente en Skype Empresarial Server
 
**Resumen:** Modifique una directiva de PIN existente en Skype Empresarial Server.
  
Puede usar la pestaña Directiva de **PIN** para proporcionar autenticación de número de identificación personal (PIN) a los usuarios que se conectan a Skype Empresarial con teléfonos IP. Para usar la autenticación PIN, asegúrese de que la opción **Habilitar autenticación PIN** esté seleccionada en la configuración del servicio web.
  
Siga estos pasos para modificar una directiva de PIN de nivel de usuario o de sitio. 
  
### <a name="to-modify-an-existing-pin-policy"></a>Para modificar una directiva de PIN existente

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.
    
4. En la página **Directiva de PIN**, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
5. En **Editar directiva de PIN**, en **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que desea permitir. La longitud mínima predeterminada es de cinco dígitos.
    
6. Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla **Especificar máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.
    
7. Si activa la casilla **Especificar máximo de intentos de inicio de sesión** en **Máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.
    
8. Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.
    
9. Si activa la casilla **Habilitar expiración de PIN**, en **el PIN expira después de (días)**; escriba o seleccione el número de días después de los cuales expira el PIN.
    
10. En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar el PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.
    
11. Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, números secuenciales y conjuntos repetitivos de números, active la casilla de verificación **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.
    
    > [!IMPORTANT]
    > Se recomienda no permitir patrones comunes. 
  
12. Haga clic en **Confirmar**.
    

