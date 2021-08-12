---
title: 'Implementar el almacén de contactos unificado en Skype Empresarial Server '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Resumen: habilite el almacén de contactos unificado en Skype Empresarial Server.'
ms.openlocfilehash: 6311b760daf2c397cfc5c75ddeb5e28fd2fb6503c0c2db11ef9ed6de71a7562e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310019"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Implementar el almacén de contactos unificado en Skype Empresarial Server
 
**Resumen:** Habilite el almacén de contactos unificado en Skype Empresarial Server.
  
La habilitación del almacén de contactos unificado Skype Empresarial Server no requiere ninguna configuración de topología. Para habilitar el almacén de contactos unificado para los usuarios:
  
- La directiva de almacén de contactos unificados está habilitada (que es el comportamiento predeterminado).
    
- Los usuarios inician sesión Skype Empresarial al menos una vez.
    
Una vez migrados los contactos de un usuario, lo que ocurre automáticamente cuando un usuario inicia sesión con Skype Empresarial, el usuario puede acceder y administrar sus contactos de Skype Empresarial desde Skype Empresarial, Outlook 2013 o Outlook Web Access. El usuario no tiene que iniciar sesión para Skype Empresarial administrar sus contactos desde Outlook o Outlook Web Access.
  
> [!IMPORTANT]
> Si un usuario inicia sesión desde Skype Empresarial después de la migración, los contactos y grupos están disponibles y actualizados, pero el usuario no puede administrar (es decir, agregar, eliminar, mover, etiquetar, desetiquear o modificar) esos contactos. 
  
## <a name="enable-users-for-unified-contact-store"></a>Habilitar usuarios para el almacén de contactos unificado

Al implementar Skype Empresarial Server y publicar la topología, el almacén de contactos unificado está habilitado para todos los usuarios de forma predeterminada. No es necesario realizar ninguna acción adicional para habilitar el almacén de contactos unificado después de implementar Skype Empresarial Server. Sin embargo, puede usar el cmdlet **Set-CsUserServicesPolicy** para personalizar qué usuarios tienen disponible el almacén de contactos unificados. Puede habilitar esta característica globalmente, por sitio, por inquilino o por individuos o grupos de individuos.
  
### <a name="to-enable-users-for-unified-contact-store"></a>Procedimiento para habilitar usuarios para el almacén de contactos unificados

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** en Todos los **programas,** haga clic en **Skype Empresarial** y, a continuación, haga clic **en Skype Empresarial Server Shell de administración**.
    
2. Siga uno de estos procedimientos:
    
   - Para habilitar el almacén de contactos unificado globalmente para todos los Skype Empresarial Server usuarios, entre el siguiente cmdlet en la Windows PowerShell de línea de comandos:
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - Para habilitar el almacén de contactos unificado para los usuarios de un sitio específico, en el símbolo del sistema, escriba:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   Por ejemplo:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - Para habilitar el almacén de contactos unificado por inquilino, en el símbolo del sistema, escriba:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   Por ejemplo:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - Para habilitar el almacén de contactos unificado para usuarios específicos, en el símbolo del sistema, escriba:
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > También puede usar alias de usuario o URI de SIP en lugar del nombre para mostrar del usuario. 
  
    Por ejemplo:
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > En el ejemplo anterior, el primer comando crea una nueva directiva por usuario denominada Usuarios habilitados para UC con el indicador UcsAllowed establecido en Verdadero. El segundo comando asigna la directiva al usuario con el nombre para mostrar Ken Myer, lo cual significa que Ken Myer ahora está habilitado para el almacén de contactos unificados.
  
## <a name="migrate-users-to-unified-contact-store"></a>Migrar usuarios al almacén de contactos unificado

Los contactos de un usuario se migran automáticamente al servidor Exchange 2013 cuando el usuario:
  
- Tiene asignado una directiva de servicios del usuario que tiene UcsAllowed configurado en True.
    
- Se ha aprovisionado con un buzón Exchange 2013 y ha iniciado sesión en el buzón al menos una vez.
    
- Inicia sesión con un Skype Empresarial enriquecido.
    
Si el usuario inicia sesión con un cliente lync o anterior, o si el usuario no está conectado a un servidor de Exchange 2013, se omite la directiva de servicios de usuario y los contactos del usuario permanecen en Skype Empresarial Server.
  
Puede determinar si se han migrado los contactos de un usuario usando uno de los métodos siguientes: 
  
- Compruebe la siguiente clave del registro en el equipo cliente:
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<\\ URL SIP \> \UCS
    
    Si los contactos del usuario se almacenan en Exchange 2013, esta clave contiene un valor de InUCSMode con un valor de 2165.
    
- Ejecute el cmdlet **Test-CsUnifiedContactStore**. En la línea Skype Empresarial Server comandos del Shell de administración, escriba:
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Si el cmdlet **Test-CsUnifiedContactStore** se lleva a cabo con éxito, quiere decir que los contactos del usuario se han migrado al almacén de contactos unificado.
    
## <a name="roll-back-migrated-users"></a>Revertir usuarios migrados

Si necesita revertir la característica de almacén de contactos unificado, revierte los contactos solo si vuelve a mover al usuario a Exchange 2010 o Lync Server 2010. Para hacer la reversión, deshabilite la directiva del usuario y ejecute el cmdlet **Invoke-CsUcsRollback**. Ejecutar solo **Invoke-CsUcsRollback** no es suficiente para que la reversión sea permanente, porque la migración del almacén de contactos unificado se iniciará de nuevo si la directiva no se deshabilita. Por ejemplo, si un usuario se revierte porque Exchange 2013 se revierte Exchange Exchange 2010 y, a continuación, el buzón del usuario se mueve Exchange Exchange 2013, la migración del almacén de contactos unificado se iniciará de nuevo siete días después de la reversión, siempre que el almacén de contactos unificado aún esté habilitado para el usuario en la directiva de servicios de usuario.
  
El cmdlet **Move-CsUser** revierte automáticamente el almacén de contactos del usuario de Exchange 2013 a Skype Empresarial Server en las siguientes situaciones:
  
- Cuando los usuarios se mueven de Skype Empresarial Server a Microsoft Lync Server 2013 o Lync Server 2010. 
    
- Cuando los usuarios se migran entre locales, como cuando se mueve un usuario de Skype Empresarial Online a Skype Empresarial Server local o viceversa.
    
La importación de datos del almacén de contactos unificado desde una base de datos de copia de seguridad puede dañar los datos del almacén de contactos unificado y del usuario si el modo de almacén de contactos unificado cambia entre la exportación y la importación. Por ejemplo:
  
- Si exporta listas de contactos antes de que los contactos de los usuarios se migren a Exchange 2013 y, después de la migración, importe los mismos datos, los datos del almacén de contactos unificados y las listas de contactos se dañarán.
    
- Si exporta datos de usuario después de migrar usuarios a Exchange 2013, revierte la migración y, por algún motivo, importa los datos después de la migración, los datos del almacén de contactos unificados y las listas de contactos se dañarán.
    
> [!IMPORTANT]
> Antes de mover un buzón de Exchange de Exchange 2013 a Exchange 2010, el administrador de Exchange debe asegurarse de que el administrador de Skype Empresarial Server revierte primero los contactos de usuario de Skype Empresarial Server de Exchange 2013 a Skype Empresarial Server. Para revertir los contactos del almacén de contactos unificados a Skype Empresarial Server, consulte el procedimiento "Para revertir los contactos del almacén de contactos unificados de Exchange 2013 a Skype Empresarial Server", más adelante en esta sección. 
  
 **Cómo revertir contactos de usuario:** Si usa el cmdlet **Move-CsUser** para mover usuarios entre Skype Empresarial Server 2015 y Lync Server 2010, puede omitir estos pasos porque el cmdlet **Move-CsUser** revierte automáticamente el almacén de contactos unificado cuando mueve usuarios de Skype Empresarial Server 2015 a Lync Server 2010. **Move-CsUser** no deshabilita la directiva de almacén de contactos unificado, por lo que la migración al almacén de contactos unificado se repetirá si el usuario vuelve a Skype Empresarial Server 2015.
  

