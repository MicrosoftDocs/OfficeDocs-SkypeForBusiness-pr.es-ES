---
title: Configurar Skype empresarial Server para usar el archivado de Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Resumen: Configure las transcripciones de mensajes instantáneos para Exchange Server 2016 o Exchange Server 2013 y Skype empresarial Server.'
ms.openlocfilehash: d8d97fc455521b2557064a683f7b19553a9642d3
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797011"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Configurar Skype empresarial Server para usar el archivado de Exchange Server

**Resumen:** Configure las transcripciones de mensajes instantáneos para Exchange Server 2016 o Exchange Server 2013 y Skype empresarial Server.

Skype empresarial Server proporciona a los administradores la opción de hacer que los mensajes instantáneos y las transcripciones de conferencias web se archiven en el buzón de un usuario de Exchange Server 2016 o de Exchange Server 2013, en lugar de una base de datos de SQL Server. Si se habilita esta opción, las transcripciones se escribirán en la carpeta Purga del buzón del usuario. La carpeta Purga es una carpeta oculta que se encuentra en la carpeta Elementos recuperables. Aunque esta carpeta no está visible para los usuarios finales, la carpeta la indiza el motor de búsqueda de Exchange y se puede detectar mediante la búsqueda de buzones de Exchange y/o Microsoft SharePoint Server 2013. Debido a que la información se almacena en la misma carpeta que usa la característica de conservación local de Exchange (responsable de archivar el correo electrónico y otras comunicaciones de Exchange), los administradores pueden usar una única herramienta para buscar todas las comunicaciones electrónicas archivadas para un usuario.

> [!IMPORTANT]
> Para deshabilitar completamente el archivado de conversaciones, hay que deshabilitar también el historial de conversaciones. Para obtener más información, vea los temas siguientes: [Administración del archivado de comunicaciones internas y externas en Skype empresarial Server](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [New-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)y [set-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Para archivar transcripciones a Exchange Server, debe comenzar con la configuración de la autenticación de servidor a servidor entre Skype empresarial Server y Exchange Server. Una vez que se haya habilitado la autenticación de servidor a servidor, podrá realizar las siguientes tareas en Skype empresarial Server (tenga en cuenta que, según la configuración y la configuración, es posible que no tenga que completar todas estas tareas):

1. Habilite el archivado de Exchange modificando los ajustes de configuración de archivado de Skype empresarial Server. Este paso es obligatorio en todas las implementaciones.

2. Habilite el archivado de comunicaciones externas/internas de los usuarios. Este paso es obligatorio en todas las implementaciones.

3. Configure la propiedad ExchangeArchivingPolicy de cada usuario. Este paso solo es necesario si Skype empresarial Server y Exchange Server se encuentran en bosques diferentes.

## <a name="step-1-enabling-exchange-archiving"></a>Paso 1: habilitar el archivado de Exchange

El archivado en Skype empresarial Server se administra principalmente mediante las opciones de configuración de archivado. Al instalar Skype empresarial Server, se le otorga automáticamente una sola recopilación global de esta configuración. (Los administradores pueden, opcionalmente, crear nuevas colecciones de opciones de archivado en el ámbito del sitio). De forma predeterminada, el archivado no está habilitado en la configuración global ni está habilitado el archivado de Exchange en esta configuración. Para poder usar el archivado de Exchange, los administradores deben configurar las propiedades EnableArchiving y EnableExchangeArchiving en estas opciones de configuración. La propiedad EnableArchiving se puede establecer en uno de estos tres valores posibles:

- **None**. El archivado está deshabilitado. Este es el valor predeterminado. Si EnableArchiving se establece en ninguno, no se archivará nada en la base de datos de archivado de Skype empresarial Server ni en Exchange Server.

- **Solo**. Solo se archivan las transcripciones de mensajes instantáneos. Si el archivado de Exchange está habilitado, estas transcripciones se archivarán en Exchange Server. Si el archivado de Exchange está deshabilitado, estas transcripciones se archivarán en Skype empresarial Server.

- **ImAndWebConf**. Se archivan las transcripciones de mensajes instantáneos y las transcripciones de conferencias por Internet. Si está habilitado el archivado de Exchange, estas transcripciones se archivarán en Exchange Server. Si el archivado de Exchange está deshabilitado, estas transcripciones se archivarán en Skype empresarial Server.

La propiedad EnableExchangeArchiving es un valor booleano: establezca EnableExchangeArchiving en true ($True) para habilitar el archivado de Exchange o establezca EnableExchangeArchiving en false ($False) para deshabilitar el archivado de Exchange. Por ejemplo, este comando permite el archivado de transcripciones de mensajería instantánea y también permite el archivado de Exchange:

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Para deshabilitar el archivado de Exchange, use un comando similar al siguiente, que permite el archivado de mensajería instantánea pero deshabilita el archivado en Exchange (es decir, las transcripciones se archivarán en Skype empresarial Server):

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Si la propiedad EnableArchiving se establece en ninguno, Skype empresarial Server no archivará la mensajería instantánea ni las transcripciones de conferencias por Internet. En este caso, el servidor simplemente ignorará el valor configurado de la propiedad EnableExchangeArchiving.

El archivado de Exchange también se puede habilitar (o deshabilitar) con Skype empresarial Server. Para ello, haga lo siguiente:

1. En el Panel de control, haga clic en **Supervisión y archivado** y, luego, en **Configuración de archivado**.

2. En la pestaña **Configuración de archivado**, haga doble clic en la recopilación de opciones de archivado que quiera modificar (por ejemplo, **Global**).

3. En el panel **Editar configuración de archivado**, haga clic en la lista desplegable **Configuración de archivado** y seleccione **Archivar sesiones de mensajería instantánea** (para archivar solo las sesiones de mensajería instantánea) o **Archivar sesiones de mensajería instantánea y conferencias web** (para archivar las sesiones tanto de conferencia web como de mensajería instantánea).

4. Después de elegir los elementos para archivar, seleccione la casilla **integración de Exchange Server** para habilitar el archivado de Exchange. Para deshabilitar el archivado de Exchange, desactive esta casilla.

> [!NOTE]
> La casilla **Integración de Exchange Server** no estará disponible si la opción **Configuración de archivado** está establecida en **Deshabilitar archivado**. Debe habilitar primero el archivado y, después, habilitar el archivado de Exchange.

Si Skype empresarial Server y Exchange Server se encuentran en el mismo bosque, el archivado para usuarios individuales (o al menos para los usuarios que tienen cuentas de correo electrónico en Exchange Server) se administra mediante las directivas de retención local de Exchange. Si tiene usuarios alojados en una versión anterior de Exchange, el archivado de esos usuarios se administrará mediante las directivas de archivado de Skype empresarial Server. Tenga en cuenta que solo los usuarios con cuentas en Exchange Server 2016 o Exchange Server 2013 pueden archivar sus transcripciones de Skype empresarial en Exchange.

Si Skype empresarial Server y Exchange Server se encuentran en diferentes bosques, el archivado para usuarios individuales se administra mediante la configuración de la propiedad ExchangeArchivingPolicy para cada cuenta de usuario individual. Mire el paso 3 para más información.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Paso 2: habilitar el archivado de comunicaciones internas o externas

Una vez que haya habilitado el archivado (y el archivado de Exchange), debe modificar las directivas de archivado apropiadas para asegurarse de que las sesiones de usuario se hayan archivado realmente. Tenga en cuenta que simplemente habilitar el archivado (paso 1) no hace que Skype empresarial Server comience a archivar la mensajería instantánea y las transcripciones de conferencias por Internet. Hay que usar directivas de archivado para habilitar el archivado externo o interno. Al instalar Skype empresarial Server, también se instala una única directiva de archivado global que contiene dos propiedades:

- **ArchiveInternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones internas (solo las sesiones de los usuarios que tienen cuentas de Active Directory en la organización).

- **ArchiveExternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones externas (sesiones en las que al menos un usuario no tiene una cuenta de Active Directory en la organización).

Los valores de estas propiedades están establecidos de forma predeterminada en False, lo que implica que no se archivan las sesiones de comunicaciones ni internas ni externas. Para modificar la directiva global, puede usar el shell de administración de Skype empresarial Server y el cmdlet Set-CsArchivingPolicy. El siguiente comando habilita el archivado de las sesiones de comunicaciones internas y externas:

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

Otra opción consiste en usar el cmdlet New-CsArchivingPolicy para crear una directiva para el sitio o por usuario. Por ejemplo, este comando permite crear una directiva de archivado específica para un usuario con el nombre RedmondArchivingPolicy:

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

Si crea una directiva específica para un usuario, necesitará asignar dicha directiva a los usuarios correspondientes. Por ejemplo:

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

Las directivas de archivado también se pueden administrar con el panel de control de Skype empresarial Server. Desde el Panel de control, haga clic en **Supervisión y archivado** y haga clic en **Directiva de archivado**. Para modificar una directiva existente, haga doble clic en la directiva (por ejemplo, Global) y, en el panel **Editar directiva de archivado**, active o desactive las casillas **Archivar comunicaciones internas** o **Archivar comunicaciones externas**, según sea necesario. Para crear una nueva Directiva de archivado, haga clic en **nuevo** y, a continuación, seleccione **Directiva del sitio** o **Directiva de usuario**. Si crea una directiva de usuario, necesitará tener acceso a las cuentas de usuario correspondientes (desde la pestaña **Usuarios**) y asignar la nueva directiva a dichos usuarios.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Paso 3: configurar la propiedad ExchangeArchivingPolicy

Si Skype empresarial Server y Exchange Server se encuentran en diferentes bosques, no basta con que simplemente habilite el archivado de Exchange en la configuración de archivado; eso no hará que los mensajes instantáneos y las transcripciones de conferencias web se archiven en Exchange. En su lugar, también debe configurar la propiedad ExchangeArchivingPolicy en cada una de las cuentas de usuario de Skype empresarial Server correspondientes. Esta propiedad se puede establecer en uno de los cuatro valores posibles:

1. **Sin inicializar**. Indica que el archivado se basará en la configuración de conservación local configurada para el buzón del usuario de Exchange. Si no se ha habilitado la retención local en el buzón del usuario, el usuario tendrá archivada su mensajería y sus expedientes de conferencias por Internet en Skype empresarial Server.

2. **UseLyncArchivingPolicy**. Indica que la mensajería instantánea y las transcripciones de conferencias web del usuario deben archivarse en Skype empresarial Server en lugar de en Exchange.

3. **NoArchiving**. Indica que las transcripciones de mensajería instantánea y de las conferencias web no necesitan archivarse. Tenga en cuenta que esta configuración sobrescribe las directivas de archivado de Skype empresarial asignadas al usuario.

4. **ArchivingToExchange**. Indica que la mensajería instantánea del usuario y las transcripciones de conferencias web deberían archivarse en Exchange independientemente de la configuración de retención local que tenga (o no) se haya asignado al buzón del usuario.

Por ejemplo, para configurar una cuenta de usuario de modo que la mensajería instantánea y las transcripciones de conferencias web se archiven siempre a Exchange, puede usar un comando similar al siguiente desde el shell de administración de Skype empresarial Server:

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Si desea establecer la misma directiva de archivado para un grupo de usuarios (por ejemplo, todos los usuarios hospedados en un Grupo de registradores específico), utilice un comando similar al siguiente:

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Tenga en cuenta que debe usar el shell de administración de Skype empresarial Server (y Windows PowerShell) para configurar el valor de la propiedad ExchangeArchivingPolicy. Esta propiedad no se expone a los administradores de Skype empresarial Server.

Si desea ver una lista de los usuarios a los que se ha asignado una directiva de archivado específica, use un comando similar al siguiente, que devuelve el nombre para mostrar de Active Directory de todos los usuarios para los que se ha establecido la propiedad ExchangeArchivingPolicy como Uninitialized:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

Del mismo modo, este comando devuelve el nombre para mostrar de los usuarios que no tienen la propiedad ExchangeArchivingPolicy establecida como UseLyncArchivingPolicy:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


