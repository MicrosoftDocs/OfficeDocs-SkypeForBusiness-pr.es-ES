---
title: Configurar Skype para Business Server 2015 utilizar el archivado de Exchange Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Resumen: Configurar las transcripciones IM para 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.'
ms.openlocfilehash: 280b86d223cc1dd90eb7fe7bc17e4ab3499e7f5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-skype-for-business-server-2015-to-use-exchange-server-archiving"></a>Configurar Skype para Business Server 2015 utilizar el archivado de Exchange Server
 
**Resumen:** Configurar las transcripciones IM para 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.
  
Skype para el año 2015 de Business Server ofrece a los administradores la opción de contar con mensajería instantánea y las transcripciones de conferencias Web archivadas en el buzón de un usuario de 2016 de Exchange Server o Exchange Server 2013 en lugar de una base de datos de SQL Server. Si se habilita esta opción, las transcripciones se escribirán en la carpeta Purga del buzón del usuario. La carpeta Purga es una carpeta oculta que se encuentra en la carpeta Elementos recuperables. Aunque esta carpeta no es visible para los usuarios finales, la carpeta se indiza por el motor de búsqueda de Exchange y se puede descubrir mediante el uso de búsqueda del buzón de Exchange o Microsoft SharePoint Server 2013. Porque la información se almacena en la misma carpeta que utiliza la función mantenga In situ de Exchange (responsable de archiving de correo electrónico y otras comunicaciones de Exchange), los administradores pueden utilizar una única herramienta para archivan todas las comunicaciones electrónicas para buscar una usuario.
  
> [!IMPORTANT]
> Para deshabilitar completamente el archivado de conversaciones, hay que deshabilitar también el historial de conversaciones. Para obtener más información, vea los temas siguientes: [administrar el archivado de comunicaciones internas y externas en Skype para Business Server 2015](http://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [Nuevo CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)y [CsClientPolicy del conjunto](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 
  
Para archivar las transcripciones para Exchange Server debe empezar por configurar autenticación de servidor a servidor entre Skype para Business Server y Exchange Server. Una vez autenticación de servidor a servidor, a continuación, puede realizar las siguientes tareas en Skype para Business Server (Observe que, dependiendo de su instalación y configuración, no debe realizar todas estas tareas):
  
1. Habilitar el archivado de Exchange modificando su Skype para opciones de configuración de archiving Business Server. Este paso es obligatorio en todas las implementaciones.
    
2. Habilite el archivado de comunicaciones externas/internas de los usuarios. Este paso es obligatorio en todas las implementaciones.
    
3. Configure la propiedad ExchangeArchivingPolicy de cada usuario. Este paso sólo es necesario si Skype para Business Server y Exchange Server se encuentran en bosques diferentes.
    
## <a name="step-1-enabling-exchange-archiving"></a>Paso 1: Habilitar el archivado de Exchange

Archivado en Skype para Business Server principalmente se administra mediante la configuración de archivado. Al instalar Skype para Business Server reciben automáticamente una colección única y global de estos valores. (Los administradores pueden, opcionalmente, crear nuevas colecciones de configuraciones de archivado en el ámbito del sitio.) De forma predeterminada, archivado no está habilitado en la configuración global, ni archiving de Exchange está habilitado en esta configuración. Para poder utilizar archiving de Exchange, los administradores deben configurar las propiedades EnableExchangeArchiving y el EnableArchiving de estas opciones de configuración. La propiedad EnableArchiving se puede establecer en uno de tres valores posibles:
  
- **None**. El archivado está deshabilitado. Este es el valor predeterminado. Si EnableArchiving está establecida en ninguno, nada será archivada en el bien su Skype para archivar la base de datos de Business Server o en Exchange Server.
    
- **ImOnly**. Sólo las transcripciones de mensajes instantáneos se archivarán. Si está habilitado el archiving de Exchange, estos expedientes se archivarán en Exchange Server. Si está deshabilitado el archivado de Exchange se archivarán estas transcripciones a Skype para Business Server.
    
- **ImAndWebConf**. Se archivan las transcripciones de mensajes instantáneos y transcripciones de conferencias Web. Si está habilitado el archiving de Exchange estos expedientes se archivarán en Exchange Server. Si está deshabilitado el archivado de Exchange se archivarán estas transcripciones a Skype para Business Server.
    
La propiedad EnableExchangeArchiving es un valor booleano: establecer EnableExchangeArchiving en True ($True) para habilitar el archivado de Exchange o establecer EnableExchangeArchiving en False ($False) para deshabilitar el archivado de Exchange. Por ejemplo, este comando permite el archivado de las transcripciones de mensajería instantáneas y también permite el archiving de Exchange:
  
```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Para deshabilitar el archivado de Exchange, utilice un comando similar al siguiente, que habilita el archivado de mensajería instantánea, pero deshabilita el archivado a Exchange (en otras palabras, las transcripciones se archivarán en Skype para Business Server):
  
```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Si la propiedad EnableArchiving se establece en None, entonces Skype para Business Server no archivará las transcripciones de conferencias Web y mensajería instantánea en absoluto. En este caso, el servidor simplemente ignorará el valor configurado de la propiedad EnableExchangeArchiving. 
  
Archiving de Exchange también puede ser habilitada (o deshabilitada) utilizando el Skype para Business Server. Para ello, haga lo siguiente:
  
1. En el Panel de control, haga clic en **Supervisión y archivado** y, luego, en **Configuración de archivado**. 
    
2. En la pestaña **Configuración de archivado**, haga doble clic en la recopilación de opciones de archivado que quiera modificar (por ejemplo, **Global**).
    
3. En el panel **Editar configuración de archivado**, haga clic en la lista desplegable **Configuración de archivado** y seleccione **Archivar sesiones de mensajería instantánea** (para archivar solo las sesiones de mensajería instantánea) o **Archivar sesiones de mensajería instantánea y conferencias web** (para archivar las sesiones tanto de conferencia web como de mensajería instantánea).
    
4. Después de elegir los elementos que se va a archivar, seleccione la casilla de verificación de la **integración de Exchange Server** para habilitar el archivado de Exchange. Para deshabilitar Exchange archiving, desactive esta casilla de verificación.
    
> [!NOTE]
> La casilla **Integración de Exchange Server** no estará disponible si la opción **Configuración de archivado** está establecida en **Deshabilitar archivado**. Debe habilitar el archivado primero y, a continuación, habilitar el archivado de Exchange. 
  
Si Skype para Business Server y Exchange Server se encuentra en el mismo bosque, luego el archiving para usuarios individuales (o al menos para los usuarios que tienen correo electrónico cuentas en Exchange Server) se administran mediante las directivas de Exchange en el mismo lugar mantenga. Si tiene usuarios que están alojados en una versión anterior de Exchange, archiving, para aquellos usuarios se administrarán utilizando Skype para políticas de archiving Business Server. Tenga en cuenta que sólo los usuarios con cuentas de 2016 de Exchange Server o Exchange Server 2013 pueden tener su Skype para las transcripciones de negocios archivados en Exchange.
  
Si Skype para Business Server y Exchange Server se encuentra en diferentes bosques y archivado de los usuarios individuales se administra mediante la configuración de la propiedad ExchangeArchivingPolicy de cada cuenta de usuario individual. Mire el paso 3 para más información.
  
## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Paso 2: habilitar el archivado de comunicaciones internas o externas

Después de archivado está habilitado (y archiving de Exchange), a continuación, debe modificar las políticas de archiving adecuadas para asegurarse de que realmente se archivan sesiones de usuario. Tenga en cuenta que simplemente la habilitación del archivado (paso 1) no Skype para Business Server para empezar el archivado de mensajería instantánea y las transcripciones de conferencias Web. Hay que usar directivas de archivado para habilitar el archivado externo o interno. Al instalar Skype para Business Server también instalar una política de archiving único global que contiene dos propiedades:
  
- **ArchiveInternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones internas (solo las sesiones de los usuarios que tienen cuentas de Active Directory en la organización).
    
- **ArchiveExternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones externas (sesiones en las que al menos un usuario no tiene una cuenta de Active Directory en la organización).
    
Los valores de estas propiedades están establecidos de forma predeterminada en False, lo que implica que no se archivan las sesiones de comunicaciones ni internas ni externas. Para modificar la directiva global, puede utilizar el Skype para el Shell de administración de servidor empresarial y el cmdlet Set-CsArchivingPolicy. El siguiente comando habilita el archivado de las sesiones de comunicaciones internas y externas:
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

Otra opción consiste en usar el cmdlet New-CsArchivingPolicy para crear una directiva para el sitio o por usuario. Por ejemplo, este comando permite crear una directiva de archivado específica para un usuario con el nombre RedmondArchivingPolicy:
  
```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

Si crea una directiva específica para un usuario, necesitará asignar dicha directiva a los usuarios correspondientes. Por ejemplo:
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

Políticas de archiving también pueden administrarse utilizando el Skype para el Panel de Control de servidor empresarial. Desde el Panel de control, haga clic en **Supervisión y archivado** y haga clic en **Directiva de archivado**. Para modificar una directiva existente, haga doble clic en la directiva (por ejemplo, Global) y, en el panel **Editar directiva de archivado**, active o desactive las casillas **Archivar comunicaciones internas** o **Archivar comunicaciones externas**, según sea necesario. Para crear una nueva directiva de archivado, haga clic en **nuevo** y, a continuación, seleccione **Directiva de sitio** o de **la directiva de usuario**. Si crea una directiva de usuario, necesitará tener acceso a las cuentas de usuario correspondientes (desde la pestaña **Usuarios**) y asignar la nueva directiva a dichos usuarios.
  
## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Paso 3: configurar la propiedad ExchangeArchivingPolicy

Si Skype para Business Server y Exchange Server se encuentran en bosques diferentes, entonces no es suficiente permitir que simplemente Exchange archiving en la configuración de archiving; que no provocarán en mensajería instantánea y las transcripciones de conferencias Web archivadas en Exchange. En su lugar, debe configurar también la propiedad ExchangeArchivingPolicy de cada una de la pertinente Skype para cuentas de usuario de Business Server. Esta propiedad se puede establecer en uno de los cuatro valores posibles:
  
1. **Sin inicializar**. Indica que el archivado se basará en la configuración In situ mantenga configurada para el buzón de Exchange del usuario. Si se mantenga en el lugar no se habilitó en el buzón del usuario, a continuación, el usuario tendrá su mensajería y Web transcripciones de conferencia archivadas en Skype para Business Server. 
    
2. **UseLyncArchivingPolicy**. Indica que se deben archivar las transcripciones de conferencias Web y mensajería instantánea del usuario en Skype para Business Server en lugar de Exchange.
    
3. **NoArchiving**. Indica que las transcripciones de mensajería instantánea y de las conferencias web no necesitan archivarse. Tenga en cuenta que esta configuración invalida cualquier Skype para Business Server archiving directivas asignadas al usuario.
    
4. **ArchivingToExchange**. Indica que se ha asignado el usuario mensajería instantánea y conferencias Web transcripciones deben archivarse Exchange independientemente de la configuración de mantener presionado en el lugar que tiene (o no) para el buzón del usuario.
    
Por ejemplo, para configurar una cuenta de usuario de modo que siempre se archivan las transcripciones de conferencias Web y mensajería instantánea de Exchange puede utilizar un comando similar a éste desde el Skype para el Shell de administración de servidor de negocios:
  
```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Si desea establecer la misma directiva de archivado para un grupo de usuarios (por ejemplo, todos los usuarios hospedados en un Grupo de registradores específico), utilice un comando similar al siguiente:
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Tenga en cuenta que debe utilizar el Skype para el Shell de administración de servidor de negocios (y Windows PowerShell) para configurar el valor de la propiedad ExchangeArchivingPolicy. Esta propiedad no se expone a los administradores en el Skype para Business Server.
  
Si desea ver una lista de los usuarios a los que se ha asignado una directiva de archivado específica, use un comando similar al siguiente, que devuelve el nombre para mostrar de Active Directory de todos los usuarios para los que se ha establecido la propiedad ExchangeArchivingPolicy como Uninitialized:
  
```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

Del mismo modo, este comando devuelve el nombre para mostrar de los usuarios que no tienen la propiedad ExchangeArchivingPolicy establecida como UseLyncArchivingPolicy:
  
```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


