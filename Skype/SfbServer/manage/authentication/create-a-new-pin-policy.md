---
title: Crear una nueva directiva PIN en Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 'Resumen: Cree una nueva directiva de PIN en Skype para Business Server.'
ms.openlocfilehash: ac51f0c81630969ec50494914e92c8302fa7d0aa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879528"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a>Crear una nueva directiva PIN en Skype para Business Server
 
**Resumen:** Crear una nueva directiva PIN en Skype para Business Server.
  
Puede usar la página **Directiva de PIN** para proporcionar autenticación de identificación personal numérica (PIN) a los usuarios que se conectan a Skype para la empresa con teléfonos IP. Para usar la autenticación de PIN, asegúrese de que la opción **Habilitar autenticación de PIN** esté seleccionada en la configuración del servicio web.
  
Siga estos pasos para crear una directiva de PIN de nivel de usuario o de nivel de sitio. 
  
### <a name="to-create-a-user-or-site-pin-policy"></a>Para crear una directiva de PIN de usuario o sitio

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.
    
4. En la página **Directiva de PIN**, haga clic en **Nueva** y, a continuación, siga uno de los procedimientos siguientes:
    
   - Para crear una directiva de nivel de usuario, haga clic en **Directiva de usuario**. En **Nueva directiva de PIN**, en   **Nombre**, escriba un nombre descriptivo para la directiva.
    
   - Para crear una directiva de nivel de sitio, haga clic en **Directiva de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba todo o parte del nombre del sitio para el que desea crear una directiva. En la lista resultante de sitios, haga clic en el sitio de su interés y, a continuación, haga clic en **Aceptar**.
    
5. En el campo **Descripción**, escriba una descripción de la directiva de PIN.
    
6. En el campo **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que desee permitir. La longitud mínima predeterminada es de cinco dígitos.
    
7. Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla   **Especificar número máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.
    
8. Si ha seleccionado la casilla **Especificar número máximo de intentos de inicio de sesión**, en **Número máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.
    
9. Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.
    
10. Si activa la casilla **Habilitar expiración de PIN**, en **El PIN expira tras (días)**, escriba o seleccione el número de días después de los cuales expira el PIN.
    
11. En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar un PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.
    
12. Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, "1234" y "8888", active la casilla **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.
    
    > [!IMPORTANT]
    > Se recomienda no permitir patrones comunes. 
  
13. Haga clic en **Confirmar**.
    

