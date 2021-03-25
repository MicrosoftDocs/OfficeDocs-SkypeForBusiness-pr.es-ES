---
title: Configurar Skype Empresarial Server para usar Exchange Server archivado
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: configure las transcripciones de mensajería instantánea para Exchange Server 2016 o Exchange Server 2013 y Skype Empresarial Server.'
ms.openlocfilehash: 43a57fc227f7fc0dbcb33b2ecb4808f3e9762ad6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120319"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Configurar Skype Empresarial Server para usar Exchange Server archivado

**Resumen:** Configurar transcripciones de mensajería instantánea para Exchange Server 2016 o Exchange Server 2013 y Skype Empresarial Server.

Skype Empresarial Server ofrece a los administradores la opción de archivar transcripciones de mensajería instantánea y conferencia web en el buzón de correo de Exchange Server 2016 o Exchange Server 2013 de un usuario en lugar de una base de datos SQL Server. Si se habilita esta opción, las transcripciones se escribirán en la carpeta Purga del buzón del usuario. La carpeta Purga es una carpeta oculta que se encuentra en la carpeta Elementos recuperables. Aunque esta carpeta no es visible para los usuarios finales, el motor de búsqueda de Exchange indiza la carpeta y se puede detectar mediante la búsqueda de buzones de Exchange o Microsoft SharePoint Server 2013. Dado que la información se almacena en la misma carpeta usada por la característica de retención de Exchange In-Place (responsable de archivar el correo electrónico y otras comunicaciones de Exchange), los administradores pueden usar una sola herramienta para buscar todas las comunicaciones electrónicas archivadas para un usuario.

> [!IMPORTANT]
> Para deshabilitar completamente el archivado de conversaciones, también debes deshabilitar el historial de conversaciones. Para obtener más información, vea los temas siguientes: [Managing the Archiving of internal and external communications in Skype for Business Server](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications), [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps)y [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Para archivar transcripciones en Exchange Server debe empezar configurando la autenticación de servidor a servidor entre Skype Empresarial Server y Exchange Server. Una vez que se haya configurado la autenticación de servidor a servidor, puede llevar a cabo las siguientes tareas en Skype Empresarial Server (tenga en cuenta que, según la configuración y la configuración, es posible que no tenga que completar todas estas tareas):

1. Habilite el archivado de Exchange modificando las opciones de configuración de archivado de Skype Empresarial Server. Este paso es obligatorio para todas las implementaciones.

2. Habilite el archivado de comunicaciones externas/internas de los usuarios. Este paso es obligatorio para todas las implementaciones.

3. Configure la propiedad ExchangeArchivingPolicy para cada usuario. Este paso solo es necesario si Skype Empresarial Server y Exchange Server están ubicados en bosques diferentes.

## <a name="step-1-enabling-exchange-archiving"></a>Paso 1: Habilitar el archivado de Exchange

El archivado en Skype Empresarial Server se administra principalmente mediante las opciones de configuración de archivado. Al instalar Skype Empresarial Server, se le asigna automáticamente una única colección global de esta configuración. (Los administradores pueden crear, opcionalmente, nuevas colecciones de opciones de archivado en el ámbito del sitio). De forma predeterminada, el archivado no está habilitado en la configuración global ni el archivado de Exchange está habilitado en esta configuración. Para usar el archivado de Exchange, los administradores deben configurar las propiedades EnableArchiving y EnableExchangeArchiving en estas opciones de configuración. La propiedad EnableArchiving se puede establecer en uno de los tres valores posibles:

- **Ninguno**. El archivado está deshabilitado. Este es el valor predeterminado. Si EnableArchiving se establece en Ninguno, no se archivará nada en la base de datos de archivado de Skype Empresarial Server o en Exchange Server.

- **ImOnly**. Solo se archivarán las transcripciones de mensajería instantánea. Si el archivado de Exchange está habilitado, estas transcripciones se archivarán en Exchange Server. Si el archivado de Exchange está deshabilitado, estas transcripciones se archivarán en Skype Empresarial Server.

- **ImAndWebConf**. Se archivarán las transcripciones de mensajería instantánea y de las conferencias web. Si el archivado de Exchange está habilitado, estas transcripciones se archivarán en Exchange Server. Si el archivado de Exchange está deshabilitado, estas transcripciones se archivarán en Skype Empresarial Server.

La propiedad EnableExchangeArchiving es un valor booleano: establezca EnableExchangeArchiving en True ($True) para habilitar el archivado de Exchange o establecer EnableExchangeArchiving en False ($False) para deshabilitar el archivado de Exchange. Por ejemplo, este comando habilita el archivado de transcripciones de mensajería instantánea y también habilita el archivado de Exchange:

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Para deshabilitar el archivado de Exchange, use un comando similar al siguiente, que habilita el archivado de mensajería instantánea pero deshabilita el archivado en Exchange (es decir, las transcripciones se archivarán en Skype Empresarial Server):

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Si la propiedad EnableArchiving está establecida en None, Skype Empresarial Server no archivará en absoluto las transcripciones de mensajería instantánea y conferencia web. En este caso, el servidor simplemente ignorará el valor configurado de la propiedad EnableExchangeArchiving.

El archivado de Exchange también se puede habilitar (o deshabilitar) con Skype Empresarial Server. Para ello, lleve a cabo el procedimiento siguiente:

1. En el Panel de control, haga clic en **Configuración y archivado** y, a continuación, en **Configuración de archivado**.

2. En la pestaña **Configuración de archivado**, haga doble clic en la recopilación de opciones de archivado que desea modificar (por ejemplo, la recopilación **Global**).

3. En el panel **Editar configuración de archivado**, haga clic en la lista desplegable **Configuración de archivado** y seleccione **Archivar sesiones de mensajería instantánea** (para archivar solo las sesiones de mensajería instantánea) o **Archivar sesiones de mensajería instantánea y conferencias web** (para archivar tanto las sesiones de conferencia web y mensajería instantánea).

4. Después de elegir los elementos que se archivarán, active la casilla **Exchange Server integración para** habilitar el archivado de Exchange. Para deshabilitar el archivado de Exchange, desactive esta casilla.

> [!NOTE]
> La casilla **Integración con Exchange Server** no estará disponible si la opción **Configuración de archivado** está configurada como **Deshabilitar archivado**. Primero debe habilitar el archivado y, a continuación, habilitar el archivado de Exchange.

Si Skype Empresarial Server y Exchange Server se encuentran en el mismo bosque, el archivado para usuarios individuales (o al menos para usuarios que tienen cuentas de correo electrónico en Exchange Server) se administra mediante las directivas de retención de Exchange In-Place. Si tiene usuarios que se encuentran en una versión anterior de Exchange, el archivado de esos usuarios se administrará mediante directivas de archivado de Skype Empresarial Server. Tenga en cuenta que solo los usuarios con cuentas en Exchange Server 2016 o Exchange Server 2013 pueden archivar sus transcripciones de Skype Empresarial en Exchange.

Si Skype Empresarial Server y Exchange Server están ubicados en bosques diferentes, el archivado de usuarios individuales se administra configurando la propiedad ExchangeArchivingPolicy para cada cuenta de usuario individual. Vea el paso 3 para obtener más información.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Paso 2: Habilitación del archivado de comunicaciones internas o externas

Después de habilitar el archivado (y el archivado de Exchange), debe modificar las directivas de archivado adecuadas para asegurarse de que las sesiones de usuario se archivan realmente. Tenga en cuenta que la simple habilitación del archivado (paso 1) no hace que Skype Empresarial Server comience a archivar la mensajería instantánea y las transcripciones de conferencia web. En su lugar, debe usar directivas de archivado para habilitar el archivado externo o interno. Al instalar Skype Empresarial Server, también se instala una única directiva de archivado global que contiene dos propiedades:

- **ArchiveInternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones internas (solo las sesiones de los usuarios de su organización que dispongan de cuentas de Active Directory).

- **ArchiveExternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones externas (sesiones en las que al menos usuario de su organización no disponga de cuenta de Active Directory).

De forma predeterminada, estos valores de propiedades están establecidos como False, lo que implica que no se archivan ni las sesiones de comunicaciones internas ni externas. Para modificar la directiva global, puede usar el Shell de administración de Skype Empresarial Server y el cmdlet Set-CsArchivingPolicy. El comando siguiente habilita el archivado de las sesiones de comunicaciones internas y externas:

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

De forma alternativa, puede usar el cmdlet New-CsArchivingPolicy para crear una nueva directiva para el sitio o por usuario. Por ejemplo, este comando permite crear una directiva de archivado específica para un usuario con el nombre RedmondArchivingPolicy:

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

Si crea una directiva específica para un usuario, necesitará asignar dicha directiva a los usuarios correspondientes. Por ejemplo:

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

Las directivas de archivado también se pueden administrar mediante el Panel de control de Skype Empresarial Server. Desde el Panel de control, haga clic en **Supervisión  y archivado** y haga clic en **Directiva de archivado**. Para modificar una directiva existente, haga doble clic en la directiva (por ejemplo, Global) y, a continuación, en el panel **Editar directiva de archivado**, active o desactive las casillas **Archivar comunicaciones internas** o **Archivar comunicaciones externas** según sea necesario. Para crear una nueva directiva de archivado, haga clic en **Nuevo** y, a continuación, seleccione **Directiva de sitio** o Directiva de **usuario.** Si crea una nueva directiva de usuario, deberá tener acceso a las cuentas de usuario correspondientes (desde la pestaña **Usuarios**) y asignar dichos usuarios a la nueva directiva.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Paso 3: Configuración de la propiedad ExchangeArchivingPolicy

Si Skype Empresarial Server y Exchange Server están ubicados en bosques diferentes, no basta con habilitar simplemente el archivado de Exchange en las opciones de configuración de archivado; que no dará lugar a que las transcripciones de mensajería instantánea y conferencia web se archiven en Exchange. En su lugar, también debe configurar la propiedad ExchangeArchivingPolicy en cada una de las cuentas de usuario relevantes de Skype Empresarial Server. Esta propiedad puede establecerse con uno de los cuatro valores posibles:

1. **Sin inicializar**. Indica que el archivado se basará en la configuración de In-Place de espera configurada para el buzón de Exchange del usuario; si In-Place la retención no se ha habilitado en el buzón del usuario, el usuario tendrá sus transcripciones de mensajería y conferencia web archivadas en Skype Empresarial Server.

2. **UseLyncArchivingPolicy**. Indica que las transcripciones de mensajería instantánea y conferencia web del usuario deben archivarse en Skype Empresarial Server en lugar de en Exchange.

3. **NoArchiving**. Indica que las transcripciones de mensajería instantánea y de las conferencias web no deben archivarse. Tenga en cuenta que esta configuración invalida las directivas de archivado de Skype Empresarial Server asignadas al usuario.

4. **ArchivingToExchange**. Indica que las transcripciones de mensajería instantánea y conferencia web del usuario deben archivarse en Exchange independientemente de la configuración de retención de In-Place que se haya asignado (o no) al buzón del usuario.

Por ejemplo, para configurar una cuenta de usuario para que las transcripciones de mensajería instantánea y conferencia web siempre se archiven en Exchange, puede usar un comando similar al siguiente desde el Shell de administración de Skype Empresarial Server:

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Si desea establecer la misma directiva de archivado para un grupo de usuarios (por ejemplo, todos los usuarios hospedados en un Grupo de registradores específico), utilice un comando similar al siguiente:

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Tenga en cuenta que debe usar el Shell de administración de Skype Empresarial Server (y Windows PowerShell) para configurar el valor de la propiedad ExchangeArchivingPolicy. Esta propiedad no se expone a los administradores de Skype Empresarial Server.

Si desea ver una lista de los usuarios a los que se ha asignado una directiva de archivado específica, utilice un comando similar al siguiente, que devuelve el nombre para mostrar de Active Directory de todos los usuarios para los que se ha establecido la propiedad ExchangeArchivingPolicy como Uninitialized:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

Del mismo modo, este comando devuelve el nombre para mostrar de los usuarios que no tienen la propiedad ExchangeArchivingPolicy establecida como UseLyncArchivingPolicy:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```