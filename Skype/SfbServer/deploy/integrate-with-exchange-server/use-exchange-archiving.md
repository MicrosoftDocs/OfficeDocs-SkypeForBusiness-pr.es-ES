---
title: Configuración de Skype para Business Server usar el archivado de Exchange Server
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
description: 'Resumen: Configure transcripciones de mensajería instantánea de Exchange Server 2016 o Exchange Server 2013 y Skype para Business Server.'
ms.openlocfilehash: 63d533091426fe609932de18e3d37bd75004ce4c
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258028"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Configuración de Skype para Business Server usar el archivado de Exchange Server

**Resumen:** Configure transcripciones de mensajería instantánea de Exchange Server 2016 o Exchange Server 2013 y Skype para Business Server.

Skype para Business Server ofrece a los administradores la opción de contar con la mensajería instantánea y transcripciones de conferencia Web archivadas al buzón de un usuario de Exchange Server 2016 o Exchange Server 2013 en lugar de una base de datos de SQL Server. Si se habilita esta opción, las transcripciones se escribirán en la carpeta Purga del buzón del usuario. La carpeta Purga es una carpeta oculta que se encuentra en la carpeta Elementos recuperables. Aunque esta carpeta no es visible para los usuarios finales, la carpeta se indiza por el motor de búsqueda de Exchange y se puede detectar mediante el uso de búsqueda de buzones de correo de Exchange o Microsoft SharePoint Server 2013. Debido a que la información se almacena en la misma carpeta que usa la característica de retención de Exchange local (responsable de archivar correo electrónico y otras comunicaciones de Exchange), los administradores pueden usar una sola herramienta para archivan todas las comunicaciones electrónicas para buscar una usuario.

> [!IMPORTANT]
> Para deshabilitar completamente el archivado de conversaciones, hay que deshabilitar también el historial de conversaciones. Para obtener más información, vea los siguientes temas: [administrar el archivado de comunicaciones internas y externas en Skype para Business Server](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)y [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Para poder archivar transcripciones para Exchange Server debe comenzar por la configuración de autenticación de servidor a servidor entre Skype para Business Server y Exchange Server. Una vez autenticación de servidor a servidor, a continuación, puede realizar las siguientes tareas en Skype para Business Server (tenga en cuenta que, dependiendo de la configuración y el programa de instalación, es posible que no necesita para llevar a cabo todas estas tareas):

1. Habilitar el archivado de Exchange mediante la modificación de su Skype para Business Server configuración de archivado. Este paso es obligatorio en todas las implementaciones.

2. Habilite el archivado de comunicaciones externas/internas de los usuarios. Este paso es obligatorio en todas las implementaciones.

3. Configure la propiedad ExchangeArchivingPolicy de cada usuario. Este paso sólo es necesario si Skype para Business Server y Exchange Server se encuentran en bosques diferentes.

## <a name="step-1-enabling-exchange-archiving"></a>Paso 1: Habilitación del archivado de Exchange

Archivado en Skype para Business Server se administra principalmente mediante el uso de la configuración de archivado. Al instalar Skype para Business Server se conceden automáticamente una colección global único de estas opciones de configuración. (Los administradores pueden, opcionalmente, crear nuevas colecciones de configuraciones de archivado en el ámbito del sitio.) De forma predeterminada, el archivado no está habilitado en la configuración global, ni archivado de Exchange está habilitado en esta configuración. Para poder usar el archivado de Exchange, los administradores deben configurar la EnableArchiving y las propiedades de EnableExchangeArchiving en estas opciones de configuración. La propiedad EnableArchiving se puede establecer en uno de tres valores posibles:

- **None**. El archivado está deshabilitado. Este es el valor predeterminado. Si EnableArchiving se establece en ninguno, a continuación, será archivar en cualquiera su Skype para base de datos de archivado de Business Server o en Exchange Server.

- **ImOnly**. Se archivan sólo las transcripciones de mensaje instantáneo. Si se habilita el archivado de Exchange, estas transcripciones se archivarán en Exchange Server. Si se deshabilita el archivado de Exchange se archivarán estas transcripciones a Skype para Business Server.

- **ImAndWebConf**. Se archivan transcripciones de mensaje instantáneo y transcripciones de conferencia Web. Si está habilitado el archivado de Exchange estas transcripciones se archivarán en Exchange Server. Si se deshabilita el archivado de Exchange se archivarán estas transcripciones a Skype para Business Server.

La propiedad EnableExchangeArchiving es un valor de tipo Boolean: establezca EnableExchangeArchiving en True ($True) para habilitar el archivado de Exchange o establecer EnableExchangeArchiving en False ($False) para deshabilitar el archivado de Exchange. Por ejemplo, este comando habilita el archivado de transcripciones de mensajería instantáneas y también habilita el archivado de Exchange:

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Para deshabilitar el archivado de Exchange, use un comando similar al siguiente, que habilita el archivado de mensajería instantánea, pero deshabilita el archivado para Exchange (en otras palabras, transcripciones se archivarán a Skype para Business Server):

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Si la propiedad EnableArchiving está establecida en ninguno, a continuación, Skype para Business Server no archiva transcripciones de conferencias Web y mensajería instantánea en absoluto. En este caso, el servidor simplemente ignorará el valor configurado de la propiedad EnableExchangeArchiving.

Archivado de Exchange puede también ser habilitado (o deshabilitado) mediante el uso de la Skype para Business Server. Para ello, haga lo siguiente:

1. En el Panel de control, haga clic en **Supervisión y archivado** y, luego, en **Configuración de archivado**.

2. En la pestaña **Configuración de archivado**, haga doble clic en la recopilación de opciones de archivado que quiera modificar (por ejemplo, **Global**).

3. En el panel **Editar configuración de archivado**, haga clic en la lista desplegable **Configuración de archivado** y seleccione **Archivar sesiones de mensajería instantánea** (para archivar solo las sesiones de mensajería instantánea) o **Archivar sesiones de mensajería instantánea y conferencias web** (para archivar las sesiones tanto de conferencia web como de mensajería instantánea).

4. Después de elegir los elementos que se va a archivar, seleccione la casilla de verificación de la **integración de Exchange Server** para habilitar el archivado de Exchange. Para deshabilitar el archivado de Exchange, desactive esta casilla de verificación.

> [!NOTE]
> La casilla **Integración de Exchange Server** no estará disponible si la opción **Configuración de archivado** está establecida en **Deshabilitar archivado**. Debe habilitar el archivado inicial y, a continuación, habilitar el archivado de Exchange.

Si Skype para Business Server y Exchange Server se encuentra en el mismo bosque, a continuación, el archivado para usuarios individuales (o al menos para los usuarios que tienen correo electrónico cuentas en Exchange Server) se administran mediante las directivas de retención de Exchange local. Si tiene usuarios que están hospedados en una versión anterior de Exchange, a continuación, el archivado para aquellos usuarios se administrarán mediante el uso de Skype para las directivas de archivado Business Server. Tenga en cuenta que sólo los usuarios con cuentas en Exchange Server 2016 o Exchange Server 2013 pueden tener su Skype para transcripciones de negocio archivados en Exchange.

Si Skype para Business Server y Exchange Server se encuentra en bosques diferentes, a continuación, el archivado para usuarios individuales se administra mediante la configuración de la propiedad ExchangeArchivingPolicy para cada cuenta de usuario individual. Mire el paso 3 para más información.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Paso 2: habilitar el archivado de comunicaciones internas o externas

Después de haber habilitado el archivado (y archivado de Exchange), a continuación, debe modificar las directivas de archivado apropiadas para asegurarse de que realmente se archivan las sesiones de usuario. Tenga en cuenta que la simple habilitación del archivado (paso 1) no causa Skype para Business Server para iniciar el archivado de mensajería instantánea y transcripciones de conferencia Web. Hay que usar directivas de archivado para habilitar el archivado externo o interno. Al instalar Skype para Business Server se instala también una directiva de archivado global único que contiene dos propiedades:

- **ArchiveInternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones internas (solo las sesiones de los usuarios que tienen cuentas de Active Directory en la organización).

- **ArchiveExternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones externas (sesiones en las que al menos un usuario no tiene una cuenta de Active Directory en la organización).

Los valores de estas propiedades están establecidos de forma predeterminada en False, lo que implica que no se archivan las sesiones de comunicaciones ni internas ni externas. Para modificar la directiva global, puede usar el Skype para Shell de administración de servidor empresarial y el cmdlet Set-CsArchivingPolicy. El siguiente comando habilita el archivado de las sesiones de comunicaciones internas y externas:

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

Directivas de archivado también pueden administrarse mediante el uso de la Skype para el Panel de Control de servidor empresarial. Desde el Panel de control, haga clic en **Supervisión y archivado** y haga clic en **Directiva de archivado**. Para modificar una directiva existente, haga doble clic en la directiva (por ejemplo, Global) y, en el panel **Editar directiva de archivado**, active o desactive las casillas **Archivar comunicaciones internas** o **Archivar comunicaciones externas**, según sea necesario. Para crear una nueva directiva de archivado, haga clic en **nuevo** y, a continuación, seleccione **Directiva de sitio** o **Directiva de usuario**. Si crea una directiva de usuario, necesitará tener acceso a las cuentas de usuario correspondientes (desde la pestaña **Usuarios**) y asignar la nueva directiva a dichos usuarios.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Paso 3: configurar la propiedad ExchangeArchivingPolicy

Si Skype para Business Server y Exchange Server se encuentran en bosques diferentes, a continuación, no es suficiente habilitar simplemente Exchange archivado en la configuración de archivado; que no se producirá en mensajería instantánea y transcripciones de conferencia Web se archiven en Exchange. En su lugar, debe configurar también la propiedad ExchangeArchivingPolicy en cada uno de los Skype relevante para las cuentas de usuario de Business Server. Esta propiedad se puede establecer en uno de los cuatro valores posibles:

1. **No inicializado**. Indica que el archivado se basará en la configuración de retención local configurada para el buzón de Exchange del usuario. Si la conservación local no se ha habilitado en el buzón del usuario, a continuación, el usuario tendrá su propia de mensajería y Web transcripciones de conferencia que se archivan en Skype para Business Server.

2. **Como UseLyncArchivingPolicy**. Indica que se deben archivar transcripciones de conferencias Web y mensajería instantánea del usuario en Skype para Business Server, en lugar de en Exchange.

3. **NoArchiving**. Indica que las transcripciones de mensajería instantánea y de las conferencias web no necesitan archivarse. Tenga en cuenta que esta configuración invalida cualquier Skype para Business Server asignadas al usuario de directivas de archivado.

4. **ArchivingToExchange**. Indica que el usuario de mensajería instantánea y conferencias Web transcripciones deben archivarse a Exchange independientemente de la configuración de retención local que tienen (o no) se han asignado para el buzón del usuario.

Por ejemplo, para configurar una cuenta de usuario para que siempre se archivan las transcripciones de conferencias Web y mensajería instantánea para Exchange puede usar un comando similar al siguiente desde el Skype para Shell de administración de servidor empresarial:

```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Si desea establecer la misma directiva de archivado para un grupo de usuarios (por ejemplo, todos los usuarios hospedados en un Grupo de registradores específico), utilice un comando similar al siguiente:

```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Tenga en cuenta que debe usar el Skype para Shell de administración de negocio Server (y Windows PowerShell) con el fin de configurar el valor de la propiedad ExchangeArchivingPolicy. Esta propiedad no se expone a los administradores en el Skype para Business Server.

Si desea ver una lista de los usuarios a los que se ha asignado una directiva de archivado específica, use un comando similar al siguiente, que devuelve el nombre para mostrar de Active Directory de todos los usuarios para los que se ha establecido la propiedad ExchangeArchivingPolicy como Uninitialized:

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

Del mismo modo, este comando devuelve el nombre para mostrar de los usuarios que no tienen la propiedad ExchangeArchivingPolicy establecida como UseLyncArchivingPolicy:

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


