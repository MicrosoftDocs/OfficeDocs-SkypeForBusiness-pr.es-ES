---
title: 'Lync Server 2013: configuración de Estados de presencia personalizados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd551ede7d7be7e631c229e99613cfc8baa006eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526997"
---
# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>Configuración de los Estados de presencia personalizados en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-10_

Para definir los Estados de presencia personalizados en Lync 2013, cree un archivo de configuración de presencia personalizada XML y, a continuación, especifique su ubicación con los cmdlets **New-CSClientPolicy** o **set-CSClientPolicy** del shell de administración de Lync Server con el parámetro CustomStateURL.

Los archivos de configuración tienen las siguientes propiedades:

  - Los Estados de presencia personalizados se pueden configurar con los indicadores de presencia disponible, ocupado y no molestar.

  - El atributo Availability determina qué indicador de presencia está asociado con el texto de estado del estado personalizado. En el ejemplo más adelante en este tema, se muestra el texto de estado Working from Home a la derecha del indicador de presencia verde (disponible).

  - La longitud máxima del texto de estado es de 64 caracteres.

  - Se pueden agregar un máximo de cuatro Estados de presencia personalizados.

  - El parámetro CustomStateURL especifica la ubicación del archivo de configuración. En Lync 2013, el modo de alta seguridad SIP está habilitado de forma predeterminada, por lo que tendrá que almacenar el archivo de configuración de presencia personalizada en un servidor Web que tenga habilitado HTTPS. De lo contrario, los clientes de Lync 2013 no podrán conectarse a él. Por ejemplo, una dirección válida sería `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml` .

<div>


> [!NOTE]  
> Aunque no se recomienda en un entorno de producción, puede probar un archivo de configuración que se encuentra en un recurso compartido de archivos distinto de HTTPS mediante la configuración del registro EnableSIPHighSecurityMode para deshabilitar el modo de alta seguridad SIP en el cliente. A continuación, puede usar la configuración del registro CustomStateURL para especificar una ubicación que no sea HTTPS para el archivo de configuración. Tenga en cuenta que Lync 2013 respeta la configuración del registro de Lync 2010, pero el subárbol del registro se ha actualizado. Crearía la configuración del registro de la siguiente manera: 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>Tipo: DWORD</P>
> <P>Datos del valor: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>Tipo: String (REG_SZ)</P>
> <P>Datos del valor (ejemplos): file:// \\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml o file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</P></LI></UL>



</div>

Localice el estado de presencia personalizado especificando uno o más esquemas de identificador de configuración regional (LCID) en el archivo de configuración XML. El ejemplo más adelante en este tema muestra la localización en inglés-Estados Unidos (1033), Noruego-Bokmål (1044), francés de Francia (1036) y Turco (1055). Para obtener una lista de LCID, consulte IDs de configuración regional asignada por Microsoft en <https://go.microsoft.com/fwlink/p/?linkid=157331> .

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a>Para agregar Estados de presencia personalizada a Lync 2013

1.  Cree un archivo de configuración XML que use el formato del ejemplo siguiente:
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  Guarde el archivo de configuración XML en un servidor Web con HTTPS habilitado. En este ejemplo, el archivo se denomina Presence.xml y se guarda en la ubicación https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml .

3.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

4.  En el shell de administración de Lync Server, defina la ubicación del archivo de configuración XML mediante un comando similar al siguiente:
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  Use el cmdlet **Grant-CSClientPolicy** para asignar esta nueva Directiva a los usuarios.

Para obtener más información, consulte [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) y [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) en la documentación del shell de administración de Lync Server.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>De forma predeterminada, Lync Server 2013 &nbsp; actualiza las directivas y la configuración del cliente cada tres horas.</P>
> <LI>
> <P>Si desea seguir usando la configuración de la Directiva de grupo de versiones anteriores, como CustomStateURL, Lync 2013 reconocerá la configuración si se encuentra en el subárbol del registro de la nueva Directiva (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync). Sin embargo, las directivas de cliente basadas en servidor tienen prioridad.</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

