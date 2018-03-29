---
title: Implementar el almacenamiento de contactos unificado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Resumen: Habilitar el almacén de contactos unificado en Skype para Business Server 2015.'
ms.openlocfilehash: fbe94023a6693f7d016d2963d49d88646c9b969e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server-2015"></a>Implementar el almacenamiento de contactos unificado en Skype Empresarial Server 2015
 
**Resumen:** Habilitar el almacén de contactos unificado en Skype para Business Server 2015.
  
Habilitar el almacén de contactos unificado en Skype para Business Server 2015 no requiere ninguna configuración de topología. Para habilitar el almacén de contactos unificado para los usuarios:
  
- La directiva del almacén de contactos unificado está habilitada (que es el comportamiento predeterminado).
    
- Los usuarios inicie sesión con Skype para el negocio al menos una vez.
    
Después de los contactos de los usuarios se han migrado, lo que sucede automáticamente cuando un usuario inicia sesión con Skype para el negocio, el usuario puede tener acceso y administrar su Skype para contactos profesionales de Skype para negocios, 2013 de Outlook o Outlook Web Access. El usuario no tiene que iniciar sesión en Skype para empresas administrar sus contactos de Outlook o Outlook Web Access.
  
> [!IMPORTANT]
> Si un usuario inicia una sesión de Skype para empresas después de la migración, contactos y grupos que están disponibles y actualizados, pero el usuario no puede administrar (que es, agregar, eliminar, mover, etiqueta, quitar la etiqueta o modificar) los contactos. 
  
## <a name="enable-users-for-unified-contact-store"></a>Habilitar usuarios para el almacenamiento de contactos unificado

Al implementar Skype para Business Server 2015 y publicar la topología, almacén de contactos unificada está habilitada de forma predeterminada para todos los usuarios. No es necesario realizar ninguna acción adicional para habilitar el almacén de contactos unificado después de implementar Skype para Business Server 2015. Sin embargo, puede utilizar el cmdlet **Set-CsUserServicesPolicy** para personalizar qué usuarios han unificado almacén de contactos disponibles. Puede habilitar esta característica globalmente, por sitio, por inquilino, por individuo o por grupos de individuos.
  
### <a name="to-enable-users-for-unified-contact-store"></a>Para habilitar usuarios para el almacén de contactos unificado

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Siga uno de estos pasos:
    
   - Para habilitar el almacén de contactos unificado globalmente para todos los Skype para los usuarios de Business Server, entre el siguiente cmdlet en la interfaz de línea de comandos de Windows PowerShell:
    
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
    > En el ejemplo anterior, el primer comando crea una nueva directiva por usuario denominada usuarios de UCS habilitados con el indicador UcsAllowed establecido en True. El segundo comando asigna la directiva al usuario con el nombre para mostrar Ken Myer, lo que significa que Ken Myer ahora está habilitado para el almacén de contactos unificado.
  
## <a name="migrate-users-to-unified-contact-store"></a>Migrar usuarios al almacén de contactos unificado

Contactos de un usuario se migran automáticamente al servidor de Exchange de 2013 cuando el usuario:
  
- Tiene asignado una directiva de servicios de usuario que tiene UcsAllowed configurado en True.
    
- Se haya aprovisionado con un buzón de Exchange de 2013 y ha iniciado sesión en el buzón al menos una vez.
    
- En los registros utilizando un Skype para cliente enriquecido de negocio.
    
Si el usuario inicia sesión con un cliente anterior o de Lync, o si el usuario no está conectado a un servidor de Exchange de 2013, se omite la directiva de servicios de usuario y los contactos del usuario permanecen en Skype para Business Server.
  
Puede determinar si se han migrado los contactos de un usuario usando uno de los métodos siguientes: 
  
- Compruebe la siguiente clave del registro en el equipo cliente:
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\< dirección URL de SIP\>\UCS
    
    Si los contactos del usuario se almacenan en Exchange 2013, esta clave contiene un valor de InUCSMode con un valor de 2165.
    
- Ejecute el cmdlet **Test-CsUnifiedContactStore** . En Skype para la línea de comandos de Shell de administración de servidor empresarial, escriba:
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Si **CsUnifiedContactStore de prueba** se realiza correctamente, se han migrado los contactos del usuario al almacén de contactos unificado.
    
## <a name="roll-back-migrated-users"></a>Revertir usuarios migrados

Si necesita revertir el contacto unificado característica de almacén, revertir los contactos sólo si el usuario se mueve de nuevo a Exchange 2010 o Lync Server 2010. Para deshacer, deshabilite la directiva para el usuario y, a continuación, ejecute el cmdlet **Invoke-CsUcsRollback** . Ejecución **Invoke-CsUcsRollback** por sí solo no es suficiente para garantizar la restauración permanente, porque el almacén de contactos unificado migración se inicia otra vez si la directiva está deshabilitada no. Por ejemplo, si un usuario es deshacer porque Exchange 2013 vuelve a Exchange 2010 y, a continuación, se mueve el buzón del usuario a Exchange de 2013, la migración del almacén de contactos unificada se inicia otra vez siete días después de la restauración, como almacenar contacto unificado todavía está habilitada para el usuario en la directiva de servicios de usuario.
  
El cmdlet **Move-CsUser** deshace automáticamente almacén de contactos del usuario de Exchange de 2013 a Skype para Business Server 2015 en las siguientes situaciones:
  
- Cuando los usuarios se mueven desde Skype para Business Server 2015 para Microsoft Lync Server 2013 o Lync Server 2010. 
    
- Cuando los usuarios se migran entre locales, como cuando un usuario se traslada de Skype para los negocios en línea a Skype para Business Server 2015 locales, o viceversa.
    
La importación de datos del almacén de contactos unificado desde una base de datos de copia de seguridad puede dañar los datos del almacén de contactos unificado y del usuario si el modo de almacén de contactos unificado cambia entre la exportación y la importación. Por ejemplo:
  
- Si exporta listas de contactos antes de que los contactos de los usuarios se migran a Exchange 2013 y a continuación, después de la migración, importación los mismos datos, se dañarán los datos de almacén de contactos unificado y listas de contactos.
    
- Si exporta datos de usuario después de migrar los usuarios a Exchange 2013, deshacer la migración y luego por algún motivo que importa los datos desde después de la migración, el contacto unificado almacenar datos y listas de contactos se dañará.
    
> [!IMPORTANT]
> Antes de mover un buzón de Exchange de 2013 de Exchange a Exchange 2010, el Administrador de Exchange debe asegurarse de que el Skype para el administrador del servidor de negocios primero revirtió el Skype para los contactos del usuario de Business Server de Exchange 2013 a Skype para Business Server. Para restaurar almacén de contactos unificado contactos en Skype para Business Server, consulte procedimiento "para revertir unificado almacén contacto contactos de Exchange de 2013 a Skype for Business Server" más adelante en esta sección. 
  
 **Cómo revertir los contactos del usuario:** Si utiliza el cmdlet **Move-CsUser** para mover usuarios entre Skype para Business Server 2015 y Lync Server 2010, puede omitir estos pasos porque el cmdlet **Move-CsUser** deshace automáticamente almacén de contactos unificada cuando mueve usuarios de Skype para Servidor de negocios 2015 a Lync Server 2010. **Mover CsUser** deshabilitar directiva de almacén de contactos unificado, por lo que se repetirá la migración al almacén unificado de contacto si el usuario se mueve al Skype para Business Server 2015.
  

