---
title: Mover usuarios locales a Skype para los negocios en línea
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: 'Resumen: Información acerca de cómo mover locales los usuarios Skype para los negocios en línea.'
ms.openlocfilehash: 9aa4c87d713af437f1fbb81cd23e354792559aa8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a>Mover usuarios locales a Skype para los negocios en línea
 
**Resumen:** Información acerca de cómo mover usuarios locales a Skype para los negocios en línea.
  
> [!CAUTION]
> Los dispositivos de Lync Phone Edition TIENEN que estar actualizados con el firmware mínimo necesario en su entorno local ANTES de migrar a Skype Empresarial Online. Si transfiere los usuarios del entorno local al entorno en línea antes de actualizar el firmware, los usuarios no se podrán conectar con sus teléfonos. Para corregir este problema, es necesario volver a transferir los usuarios al entorno local para actualizar los teléfonos con el firmware mínimo. NO INTENTE ACTUALIZAR AL FIRMWARE MÍNIMO O REALIZAR UN RESTABLECIMIENTO COMPLETO DEL TELÉFONO ANTES DE VOLVER A TRANSFERIR EL USUARIO AL ENTORNO LOCAL.
Si se realiza un restablecimiento completo cuando el dispositivo no tiene instalado el firmware mínimo, se implementará la autenticación con PIN, que no es compatible con Skype Empresarial Online. Para obtener más información, consulte [Obtención de teléfonos para Skype para los negocios en línea](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Éste es un paso opcional que sólo es necesario si va a mover usuarios locales a Skype para los negocios en línea. Antes de empezar a mover los usuarios a Skype para los negocios en línea, compruebe que se ha implementado el Skype para Business Connector en línea (módulo de Windows PowerShell) en los servidores frontales. Si no es así, puede descargarlo desde [el centro de descarga](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Además, para preparar AD tendrá que configurar Azure AD Connect. La versión de AAD Connect que tiene que usar es la versión 1.0.9125.0 o posterior. Si usa una versión anterior de las herramientas de AAD Connect o DirSync, actualice a la versión compatible. Puede actualizar la instalación actual y mantener las reglas personalizadas que haya definido en su entorno.
  
Mover usuarios utilizando cualquiera Skype para Panel de Control de servidor de negocios o Skype para el Shell de administración de servidor de negocios en la implementación de locales, pero debe tener credenciales de administrador para la implementación de Office 365.
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a>Mover usuarios con Skype para Panel de Control del negocio

### <a name="to-move-a-user-to-skype-for-business-online"></a>Para mover un usuario a Skype para los negocios en línea

1. Desde una cuenta de usuario que se asigna a la función CsUserAdministrator o CsAdministrator, iniciar sesión en cualquier equipo en la implementación interna que tenga Skype para Business Server o en menos Skype para herramientas Business Server Admin instalado.
    
2. Desde el menú Inicio o un acceso directo del escritorio, abra el Skype para el Panel de Control de servidor empresarial.
    
    También puede acceder el Skype para el Panel de Control de servidor empresarial utilizando la dirección URL de Admin si ha configurado uno.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. Haga clic en el usuario y, después, en el menú **Acción**, haga clic en **Mover usuarios seleccionados a Skype Empresarial Online**.
    
6. En la página **Mover usuarios a Skype Empresarial Online**, lea la información y, después, haga clic en **Siguiente**.
    
7. En la siguiente página, si usted no se ha iniciado sesión en Office 365, haga clic en **iniciar sesión en Office 365**, proporcionar sus credenciales y haga clic en **Aceptar** y en **siguiente**.
    
8. Confirme que el número de usuarios que se transferirán es correcto y haga clic en **Siguiente**.
    
9. En la página siguiente, revise los resultados y haga clic en **Cerrar**.
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a>Mover usuarios con Skype para el Shell de administración de servidor empresarial

Para mover un usuario local a su Skype para inquilinos de negocios en línea, ejecute los siguientes cmdlets en el Skype para el Shell de administración de servidor de negocios, utilizando las credenciales de administrador para los clientes de Microsoft Office 365. Sustituya “username@contoso.com” por la información del usuario que quiera mover.
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL para el grupo de servidores donde se ejecuta el servicio alojado de migración, en el formato siguiente: _Https://\<Pool FQDN\>/HostedMigration/ hostedmigrationService.svc_.
  
Puede determinar la dirección URL del servicio de migración alojado visualizando la dirección URL para el Skype para el centro de administración de negocios en línea para la cuenta del inquilino de Office 365.
  
> [!NOTE]
> La URL distingue mayúsculas de minúsculas. 
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365

1. Inicie sesión en el inquilino de Office 365 como administrador.
    
2. Abra el **Centro de administración de Skype Empresarial**.
    
3. Con el **Centro de administración de Skype Empresarial** abierto, seleccione y copie la dirección URL en la barra de direcciones hasta **lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación: 
    
     `https://admin0a.online.lync.com`
    
5. Anexe la cadena siguiente a la URL: **/MigraciónHospedada/ServicioDeMigraciónHospedado.svc **.
    
    La dirección URL resultante, que es el valor de la **HostedMigrationOverrideUrl**, debe tener el siguiente aspecto:
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    

