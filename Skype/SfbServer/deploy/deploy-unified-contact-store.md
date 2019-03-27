---
title: 'Implementar el almacén de contactos unificados en Skype para Business Server '
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Resumen: Habilitar el almacén de contactos unificados en Skype para Business Server.'
ms.openlocfilehash: 5e7fb34d03459be5066d154e89fa8e27dc060757
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882569"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Implementar el almacén de contactos unificados en Skype para Business Server
 
**Resumen:** Habilitar el almacén de contactos unificados en Skype para Business Server.
  
Habilitar el almacén de contactos unificados en Skype para Business Server no requiere ninguna configuración de la topología. Para habilitar el almacén de contactos unificado para los usuarios:
  
- La directiva del almacén de contactos unificado está habilitada (que es el comportamiento predeterminado).
    
- Los usuarios inicien sesión Skype para la empresa al menos una vez.
    
Después de que los contactos del usuario se han migrado, lo que sucede automáticamente cuando un usuario inicia sesión con Skype para la empresa, el usuario puede tener acceso y administrar su Skype para contactos profesionales de Skype para profesionales, 2013 de Outlook o Outlook Web Access. El usuario no debe tener una sesión iniciada Skype para la empresa administrar sus contactos de Outlook o Outlook Web Access.
  
> [!IMPORTANT]
> Si un usuario inicia sesión desde Skype para la empresa después de la migración, contactos y grupos que están disponibles y actualizados, pero el usuario no puede administrar (es decir, agregar, eliminar, mover, marcar, cómo quitar la etiqueta o modificar) los contactos. 
  
## <a name="enable-users-for-unified-contact-store"></a>Habilitar usuarios para el almacenamiento de contactos unificado

Al implementar Skype para Business Server y publicar la topología, almacén de contactos unificados está habilitado para todos los usuarios de forma predeterminada. No es necesario realizar ninguna acción adicional para habilitar el almacén de contactos unificados después de implementar Skype para Business Server. Pero, puede usar el cmdlet **Set-CsUserServicesPolicy** para personalizar qué usuarios tienen disponible el almacén de contactos unificado. Puede habilitar esta característica globalmente, por sitio, por inquilino, por individuo o por grupos de individuos.
  
### <a name="to-enable-users-for-unified-contact-store"></a>Para habilitar usuarios para el almacén de contactos unificado

1. Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para la empresa**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.
    
2. Siga uno de estos pasos:
    
   - Para habilitar el almacén de contactos unificados globalmente para todos los Skype para los usuarios de Business Server, entre el cmdlet siguiente en la interfaz de línea de comandos de Windows PowerShell:
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - Para habilitar el almacén de contactos unificado para los usuarios de un sitio específico, en el símbolo del sistema, escriba:
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   Por ejemplo:
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - Para habilitar el almacén de contactos unificado por inquilino, en el símbolo del sistema, escriba:
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   Por ejemplo:
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - Para habilitar el almacén de contactos unificado para usuarios especificados, en el símbolo del sistema, escriba:
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > También puede usar alias de usuario o URI de SIP en lugar del nombre para mostrar del usuario. 
  
    Por ejemplo:
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > En el ejemplo anterior, el primer comando crea una directiva por usuario denominada Usuarios habilitados para UCS con el indicador UcsAllowed establecido en True. El segundo comando asigna la directiva al usuario con el nombre para mostrar Ken Myer, lo que significa que Ken Myer ahora está habilitado para el almacén de contactos unificado.
  
## <a name="migrate-users-to-unified-contact-store"></a>Migrar usuarios al almacén de contactos unificado

Contactos de un usuario se migran automáticamente en el servidor de Exchange 2013 cuando el usuario:
  
- Tiene asignado una directiva de servicios de usuario que tiene UcsAllowed configurado en True.
    
- Se ha suministrado con un buzón de Exchange 2013 y ha iniciado sesión en el buzón de correo al menos una vez.
    
- Inicia sesión usando un Skype para el cliente enriquecido de negocio.
    
Si el usuario inicia sesión con un Lync o cliente anterior, o si el usuario no está conectado a un servidor de Exchange 2013, se omite la directiva de servicios de usuario y los contactos del usuario permanecen en Skype para Business Server.
  
Puede determinar si se han migrado los contactos de un usuario usando uno de los métodos siguientes: 
  
- Compruebe la siguiente clave del registro en el equipo cliente:
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\dirección URL de <SIP\>\UCS
    
    Si los contactos del usuario se almacenan en Exchange 2013, esta clave contiene un valor de InUCSMode con un valor 2165.
    
- Ejecute el cmdlet **Test-CsUnifiedContactStore**. En Skype para la línea de comandos de Shell de administración de servidor empresarial, escriba:
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Si el cmdlet **Test-CsUnifiedContactStore** se lleva a cabo con éxito, quiere decir que los contactos del usuario se han migrado al almacén de contactos unificado.
    
## <a name="roll-back-migrated-users"></a>Revertir usuarios migrados

Si es necesario revertir el contacto unificado almacenar característica, revertir los contactos sólo si el usuario se mueve de nuevo a Exchange 2010 o Lync Server 2010. Para hacer la reversión, deshabilite la directiva del usuario y ejecute el cmdlet **Invoke-CsUcsRollback**. Ejecutar solo **Invoke-CsUcsRollback** no es suficiente para que la reversión sea permanente, porque la migración del almacén de contactos unificado se iniciará de nuevo si la directiva no se deshabilita. Por ejemplo, si un usuario es deshacer porque se deshace 2013 de Exchange a Exchange 2010 y, a continuación, se mueve el buzón del usuario a Exchange 2013, la migración de almacén de contactos unificados se iniciará nuevamente siete días después de la operación de deshacer, siempre y cuando el almacén de contactos unificado aún se está habilitada para el usuario en la directiva de servicios de usuario.
  
El cmdlet **Move-CsUser** revierte automáticamente almacén de contactos del usuario de Exchange 2013 a Skype para Business Server en las situaciones siguientes:
  
- Cuando se mueven usuarios de Skype para Business Server para Microsoft Lync Server 2013 o Lync Server 2010. 
    
- Cuando se migran usuarios entre locales, como cuando un usuario se mueve de Skype para empresarial en línea para Skype para Business Server local, o viceversa.
    
La importación de datos del almacén de contactos unificado desde una base de datos de copia de seguridad puede dañar los datos del almacén de contactos unificado y del usuario si el modo de almacén de contactos unificado cambia entre la exportación y la importación. Por ejemplo:
  
- Si exporta las listas de contactos antes de que los contactos de los usuarios se migran a Exchange 2013 y, a continuación, después de la migración, importación los datos de la misma, esté dañadas los datos de almacén de contactos unificados y las listas de contactos.
    
- Si exporta datos de usuario después de migrar los usuarios a Exchange 2013, revertir la migración y, a continuación, por algún motivo importar los datos de después de la migración, el contacto unificado almacenar datos y las listas de contactos se esté dañadas.
    
> [!IMPORTANT]
> Antes de mover un buzón de Exchange desde Exchange 2013 a Exchange 2010, el Administrador de Exchange debe asegurarse de que la Skype para el administrador del servidor de negocio se primero deshecho la Skype para los contactos del usuario de Business Server desde Exchange 2013 a Skype para Business Server. Para revertir los contactos del almacén de contactos unificados a Skype para Business Server, consulte el procedimiento "para revertir los contactos del almacén de contactos unificados de Exchange 2013 para Skype for Business Server" más adelante en esta sección. 
  
 **Cómo revertir los contactos:** Si usa el cmdlet **Move-CsUser** para mover usuarios entre Skype para Business Server 2015 y Lync Server 2010, puede omitir estos pasos debido a que el cmdlet **Move-CsUser** revierte automáticamente almacén de contactos unificados cuando se desplaza a los usuarios de Skype para 2015 servidor empresarial a Lync Server 2010. **Move-CsUser** deshabilitar la directiva de almacén de contactos unificados, por lo que la migración al almacén de contactos unificado se repetirá si el usuario se mueve al Skype para Business Server 2015.
  

