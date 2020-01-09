---
title: Administrar directivas de PIN para conferencias de acceso telefónico local en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Resumen: Aprenda a administrar directivas de PIN para conferencias de acceso telefónico local en Skype empresarial Server.'
ms.openlocfilehash: f5ffef4af17a4337fe600b2059aab1ea106235ae
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992297"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>Administrar directivas de PIN para conferencias de acceso telefónico local en Skype empresarial Server
 
**Resumen:** Aprenda a administrar directivas de PIN para conferencias de acceso telefónico local en Skype empresarial Server.
  
Los usuarios de Skype empresarial Server que tienen credenciales de servicios de dominio de Active Directory (AD DS) en su organización pueden unirse a conferencias de acceso telefónico local como usuarios autenticados mediante un número de identificación personal (PIN). La directiva de PIN define las reglas de funcionamiento de los PIN de conferencias de acceso telefónico local.
  
 Si desea usar la misma directiva de PIN para toda la organización, puede usar la directiva de PIN global y modificarla según sea necesario. La directiva de PIN global define las reglas de los PIN para conferencias de acceso telefónico local en el nivel de bosque. Puede modificar la directiva de PIN global, pero no se puede eliminar.
  
Puede crear una nueva directiva de PIN si desea aplicar una directiva específica a un sitio a un grupo de usuarios determinado.
  
Las directivas de PIN se aplican a usuarios que van del ámbito más limitado al ámbito más extenso. Si asigna una directiva de PIN de usuario a un usuario, esa configuración tendrá preferencia. Si no asigna una directiva de usuario, se aplica la directiva de PIN de sitio, si existe. Si no se aplica ni la directiva de usuario ni la de sitio, la directiva de PIN global proporcionará la configuración predeterminada.
  
## <a name="view-information-about-pin-policies"></a>Ver información sobre las directivas de PIN

Puede ver información sobre las directivas de PIN con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>Ver información sobre directivas de PIN con el panel de control de Skype empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de PIN**.
    
4. En la página **Directiva de PIN**, haga clic en la directiva de PIN que desee modificar, haga clic en **Editar** y luego en **Mostrar detalles**.
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>Ver información sobre directivas de PIN mediante el shell de administración de Skype empresarial Server

Para ver información sobre las directivas de PIN, use el cmdlet **Get-CsPinPolicy**. Por ejemplo, el siguiente comando devuelve información sobre una sola directiva de PIN con el valor de Identity site:Redmond:
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, vea [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).
  
## <a name="modify-the-global-pin-policy"></a>Modificar la directiva de PIN global

Puede modificar la Directiva de PIN global mediante el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modificar la Directiva de PIN de conferencias de acceso telefónico local global mediante el panel de control de Skype empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de PIN**.
    
4. En la página **Directiva de PIN**, haga clic en **Global**, en **Editar** y después en **Mostrar detalles**.
    
5. En **Editar directiva de PIN**, en **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que desea permitir. La longitud mínima predeterminada es de cinco dígitos.
    
6. Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla   **Especificar número máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.
    
7. Si ha seleccionado la casilla **Especificar número máximo de intentos de inicio de sesión**, en **Número máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.
    
8. Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.
    
9. Si activa la casilla **Habilitar expiración de PIN**, en **El PIN expira tras (días)**, escriba o seleccione el número de días después de los cuales expira el PIN.
    
10. En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar el PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.
    
11. Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, números secuenciales y conjuntos repetitivos de números, active la casilla **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.
    
    > [!IMPORTANT]
    > Por motivos de seguridad, Microsoft recomienda que no se permitan patrones comunes. 
  
12. Haga clic en **Confirmar**.
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modificar la Directiva de PIN de conferencias de acceso telefónico local global mediante el shell de administración de Skype empresarial Server

Para modificar la directiva de PIN global de conferencias de acceso telefónico local, use el cmdlet **Set-CsPinPolicy**.
  
El siguiente comando cambia el valor de la propiedad MinPasswordLength de todas las directivas de PIN configuradas para su uso en la organización. Para ello, el comando llama primero al cmdlet **Get-CsPinPolicy** sin ningún parámetro, para recuperar una recopilación de todas las directivas de PIN existentes. Después, la recopilación se canaliza al cmdlet **Set-CsPinPolicy**, que modifica el valor de la propiedad MinPasswordLength de todas las directivas de la colección:
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, consulte [set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="create-a-user-or-site-pin-policy"></a>Crear una directiva de PIN de usuario o sitio

Puede crear una directiva de PIN de sitio o usuario mediante el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Crear una directiva de PIN de sitio o usuario con el panel de control de Skype empresarial Server

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de PIN**.
    
4. En la página **Directiva de PIN**, haga clic en **Nueva** y, a continuación, siga uno de los procedimientos siguientes:
    
   - Para crear una directiva de nivel de usuario, haga clic en **Directiva de usuario**. En **Nueva directiva de PIN**, en   **Nombre**, escriba un nombre descriptivo para la directiva.
    
   - Para crear una directiva de nivel de sitio, haga clic en **Directiva de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba todo o parte del nombre del sitio para el que desea crear una directiva. En la lista de sitios, haga clic en el sitio que desee y después en **Aceptar**.
    
5. En el campo **Descripción**, escriba una descripción de la directiva de PIN.
    
6. En el campo **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que desee permitir. La longitud mínima predeterminada es de cinco dígitos.
    
7. Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla   **Especificar número máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.
    
8. Si ha seleccionado la casilla **Especificar número máximo de intentos de inicio de sesión**, en **Número máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.
    
9. Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.
    
10. Si activa la casilla **Habilitar expiración de PIN**, en **El PIN expira tras (días)**, escriba o seleccione el número de días después de los cuales expira el PIN.
    
11. En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar el PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.
    
12. Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, números secuenciales y conjuntos repetitivos de números, active la casilla **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.
    
    > [!IMPORTANT]
    > Por motivos de seguridad, Microsoft recomienda que no se permitan patrones comunes. 
  
13. Haga clic en **Confirmar**.
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Crear una directiva de PIN de sitio o usuario con el shell de administración de Skype empresarial Server

Para crear una directiva de PIN de usuario o sitio, use el cmdlet **New-CsPinPolicy**.
  
El siguiente comando crea una directiva de PIN con el parámetro Identity site:Redmond. Este comando solo incluye un parámetro opcional, MinPasswordLength, que se usa para establecer la propiedad MinPasswordLength en 7. El resto de propiedades de la directiva se configurarán con los valores predeterminados.
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, consulte [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).
  
## <a name="modify-a-user-or-site-pin-policy"></a>Modificar una directiva de PIN de usuario o sitio

Puede modificar una directiva de PIN de sitio o usuario mediante el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modificar una directiva de PIN de usuario o de sitio con el panel de control de Skype empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de PIN**.
    
4. En la página **Directiva de PIN**, haga clic en la directiva de PIN que desee modificar, haga clic en **Editar** y después en **Mostrar detalles**.
    
5. En **Editar directiva de PIN**, modifique cualquier configuración de directivas (salvo el nombre de la directiva, que no se puede modificar).
    
6. Haga clic en **Confirmar**.
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modificar una directiva de PIN de usuario o de sitio con el shell de administración de Skype empresarial Server

Para modificar la directiva de PIN de conferencias de acceso telefónico local, use el cmdlet **Set-CsPinPolicy**.
  
El siguiente comando modifica la directiva de PIN asignada al sitio de Redmond. En este caso, el comando cambia el valor de la propiedad MinPasswordLength a 10; esto significa que los nuevos PIN necesitan contener al menos 10 dígitos:
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, consulte [set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="delete-a-user-or-site-pin-policy"></a>Eliminar una directiva de PIN de usuario o sitio

Puede eliminar una directiva de PIN de sitio o usuario mediante el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Eliminar una directiva de PIN de usuario o de sitio con el panel de control de Skype empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de PIN**.
    
4. En la página **Directiva de PIN**, haga clic en la directiva de PIN que desee modificar, haga clic en **Editar** y después en **Eliminar**.
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Eliminar una directiva de PIN de usuario o de sitio con el shell de administración de Skype empresarial Server

Para eliminar una directiva de PIN de usuario o sitio, use el cmdlet **Remove-CsPinPolicy**.
  
El siguiente comando quita todas las directivas de PIN que se han configurado en el ámbito de sitio. Para ello, use el cmdlet **Get-CsPinPolicy** junto con el parámetro Filter, para devolver una colección con todas las directivas cuyo parámetro Identity comienza por los caracteres "site:". Luego, esta colección se canaliza al cmdlet **Remove-CsPinPolicy**, que elimina las distintas directivas de la colección:
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

Para obtener más información, incluida una descripción completa de la sintaxis y una lista de parámetros, consulte [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).
  

