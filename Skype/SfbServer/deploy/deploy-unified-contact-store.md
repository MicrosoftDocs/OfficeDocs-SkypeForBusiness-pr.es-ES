---
title: 'Implementar el almacén de contactos unificado en Skype empresarial Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Resumen: habilite el almacén de contactos unificado en Skype empresarial Server.'
ms.openlocfilehash: 737e9dbdd0dc9e4aae54e454cb558c59004719b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302806"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Implementar el almacén de contactos unificado en Skype empresarial Server
 
**Resumen:** Habilitar el almacén de contactos unificado en Skype empresarial Server.
  
Habilitar el almacén de contactos unificado en Skype empresarial Server no requiere ninguna configuración de topología. Para habilitar el almacén de contactos unificado para los usuarios:
  
- La directiva del almacén de contactos unificado está habilitada (que es el comportamiento predeterminado).
    
- Los usuarios inician sesión en Skype empresarial al menos una vez.
    
Después de migrar los contactos de un usuario, que sucede automáticamente cuando un usuario inicia sesión con Skype empresarial, el usuario puede acceder a sus contactos de Skype empresarial y administrarlos desde Skype empresarial, Outlook 2013 o Outlook Web Access. El usuario no tiene que haber iniciado sesión en Skype empresarial para administrar sus contactos desde Outlook o Outlook Web Access.
  
> [!IMPORTANT]
> Si un usuario inicia sesión desde Skype empresarial después de la migración, los contactos y grupos están disponibles y actualizados, pero el usuario no puede administrarlos (es decir, agregar, eliminar, mover, etiquetar, quitar o modificar) esos contactos. 
  
## <a name="enable-users-for-unified-contact-store"></a>Habilitar usuarios para el almacenamiento de contactos unificado

Al implementar Skype empresarial Server y publicar la topología, el almacén de contactos unificado está habilitado para todos los usuarios de forma predeterminada. No es necesario realizar ninguna acción adicional para habilitar el almacén de contactos unificado después de implementar Skype empresarial Server. Pero, puede usar el cmdlet **Set-CsUserServicesPolicy** para personalizar qué usuarios tienen disponible el almacén de contactos unificado. Puede habilitar esta característica globalmente, por sitio, por inquilino, por individuo o por grupos de individuos.
  
### <a name="to-enable-users-for-unified-contact-store"></a>Para habilitar usuarios para el almacén de contactos unificado

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial**y, a continuación, haga clic en **consola de administración de Skype empresarial**.
    
2. Siga uno de estos pasos:
    
   - Para habilitar el almacén de contactos Unificado de forma global para todos los usuarios de Skype empresarial Server, en la interfaz de línea de comandos de Windows PowerShell, con el siguiente cmdlet:
    
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

Los contactos de un usuario se migran automáticamente al servidor de Exchange 2013 cuando el usuario:
  
- Tiene asignado una directiva de servicios de usuario que tiene UcsAllowed configurado en True.
    
- Se aprovisionó con un buzón de Exchange 2013 y ha iniciado sesión en el buzón al menos una vez.
    
- Inicia sesión con un cliente enriquecido de Skype empresarial.
    
Si el usuario inicia sesión con un cliente de Lync o de una versión anterior, o si el usuario no está conectado a un servidor de Exchange 2013, se ignorará la Directiva de servicios de usuario y los contactos del usuario permanecerán en Skype empresarial Server.
  
Puede determinar si se han migrado los contactos de un usuario usando uno de los métodos siguientes: 
  
- Compruebe la siguiente clave del registro en el equipo cliente:
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS
    
    Si los contactos del usuario se almacenan en Exchange 2013, esta clave contiene un valor de InUCSMode con un valor de 2165.
    
- Ejecute el cmdlet **Test-CsUnifiedContactStore**. En la línea de comandos del shell de administración de Skype empresarial Server, escriba:
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Si el cmdlet **Test-CsUnifiedContactStore** se lleva a cabo con éxito, quiere decir que los contactos del usuario se han migrado al almacén de contactos unificado.
    
## <a name="roll-back-migrated-users"></a>Revertir usuarios migrados

Si necesita revertir la característica de almacenamiento de contactos unificado, revierta los contactos solo si vuelve a colocar el usuario en Exchange 2010 o Lync Server 2010. Para hacer la reversión, deshabilite la directiva del usuario y ejecute el cmdlet **Invoke-CsUcsRollback**. Ejecutar solo **Invoke-CsUcsRollback** no es suficiente para que la reversión sea permanente, porque la migración del almacén de contactos unificado se iniciará de nuevo si la directiva no se deshabilita. Por ejemplo, si un usuario se deshace porque Exchange 2013 se ha revertido a Exchange 2010 y, a continuación, el buzón del usuario se mueve a Exchange 2013, la migración del almacén de contactos unificado se iniciará de nuevo siete días después de la reversión, siempre que el almacén de contactos unificado aún está habilitado para el usuario en la Directiva de servicios de usuario.
  
El cmdlet **Move-CsUser** revierte automáticamente el almacén de contactos del usuario de Exchange 2013 a Skype empresarial Server en las situaciones siguientes:
  
- Cuando los usuarios se mueven de Skype empresarial Server a Microsoft Lync Server 2013 o Lync Server 2010. 
    
- Cuando los usuarios migran interlocales, como cuando un usuario se mueve de Skype empresarial online a Skype empresarial Server local, o viceversa.
    
La importación de datos del almacén de contactos unificado desde una base de datos de copia de seguridad puede dañar los datos del almacén de contactos unificado y del usuario si el modo de almacén de contactos unificado cambia entre la exportación y la importación. Por ejemplo:
  
- Si exporta listas de contactos antes de migrar los contactos de los usuarios a Exchange 2013 y, después de la migración, importar los mismos datos, se dañarán los datos del almacén de contactos unificado y las listas de contactos.
    
- Si exporta los datos de usuario después de migrar los usuarios a Exchange 2013, revertir la migración y, por algún motivo, importar los datos desde después de la migración, los datos del almacén de contactos unificados y las listas de contactos estarán dañados.
    
> [!IMPORTANT]
> Antes de mover un buzón de Exchange de Exchange 2013 a Exchange 2010, el administrador de Exchange debe asegurarse de que el administrador de Skype empresarial Server haya revertido primero los contactos de usuario de Skype empresarial Server de Exchange 2013 a Skype para Business Server. Para deshacer los contactos de la tienda de contactos unificada en Skype empresarial Server, consulte el procedimiento "para revertir contactos de almacenamiento de contactos Unificado de Exchange 2013 a Skype empresarial Server", más adelante en esta sección. 
  
 **Cómo revertir contactos de usuario:** Si usa el cmdlet **Move-CsUser** para mover usuarios entre Skype empresarial Server 2015 y Lync Server 2010, puede omitir estos pasos porque el cmdlet **Move-CsUser** revierte automáticamente el almacén de contactos unificado cuando mueve usuarios de Skype para Business Server 2015 a Lync Server 2010. **Move-CsUser** no deshabilita la Directiva del almacén de contactos unificado, por lo que la migración al almacén de contactos unificado se repetirá si el usuario vuelve a usar Skype empresarial Server 2015.
  

