---
title: Configuración de estados de presencia personalizados
TOCTitle: Configuración de estados de presencia personalizados
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398997(v=OCS.15)
ms:contentKeyID: 52061899
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de estados de presencia personalizados

 

_**Última modificación del tema:** 2016-12-08_

Para definir estados de presencia personalizados en Lync 2013, cree un archivo XML de configuración de presencia personalizado y especifique su ubicación mediante los cmdlets del Shell de administración de Lync Server**New-CSClientPolicy** o **Set-CSClientPolicy** con el parámetro CustomStateURL.

Los archivos de configuración tienen las propiedades siguientes:

  - Los estados de presencia personalizados pueden configurarse con los indicadores de presencia Disponible, Ocupado y No molestar.

  - El atributo de disponibilidad determina qué indicador de presencia está asociado con el texto del estado personalizado. En el ejemplo descrito más adelante en este tema, el texto de estado Trabajando desde casa se muestra a la derecha del indicador de presencia de color verde (Disponible).

  - La longitud máxima del texto de estado es de 64 caracteres.

  - Pueden agregarse un máximo de cuatro estados de presencia personalizados.

  - El parámetro CustomStateURL especifica la ubicación del archivo de configuración. En Lync 2013, el modo SIP de alta seguridad está habilitado de forma predeterminada, de modo que el archivo de configuración de presencia personalizado deberá almacenarse en un servidor web que tenga HTTPS habilitado o, de lo contrario, los clientes de Lync 2013 no podrán conectarse a él. Una dirección válida sería, por ejemplo, `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.


> [!NOTE]
> Si bien no conviene hacerlo en un entorno de producción, se puede comprobar un archivo de configuración que se encuentra en un recurso compartido que no es HTTPS, para lo cual se usa la configuración del Registro EnableSIPHighSecurityMode para deshabilitar el modo SIP de alta seguridad en el cliente. Tras ello, se puede usar la configuración del Registro CustomStateURL para especificar una ubicación que no sea HTTPS para el archivo de configuración. Tenga en cuenta que Lync 2013 respeta la configuración del Registro de Lync 2010, aunque el subárbol del Registro se ha actualizado. La configuración del Registro se crearía de este modo: 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>Tipo: DWORD</P>
> <P>Datos del valor: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>Tipo: Cadena (REG_SZ)</P>
> <P>Datos del valor (ejemplos): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml o file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</P></LI></UL>



Localice su estado de presencia personalizado especificando uno o más esquemas de identificador de configuración regional (LCID) en el archivo de configuración XML. En el ejemplo descrito más adelante en este tema se muestra la localización en inglés - Estados Unidos (1033), noruego - Bokmål (1044), francés - Francia (1036) y turco (1055). Para obtener una lista de LCID, consulte los identificadores de configuración regional asignados por Microsoft en <http://go.microsoft.com/fwlink/?linkid=157331>.

## Para agregar estados de presencia personalizados a Lync 2013

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

2.  Guarde el archivo de configuración XML en un servidor web con HTTPS habilitado. En este ejemplo, el archivo se llama Presence.xml y se guarda en la ubicación https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.

3.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

4.  En el Shell de administración de Lync Server, defina la ubicación de su archivo de configuración XML mediante un comando similar a este:
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  Use el cmdlet **Grant-CSClientPolicy** para asignar esta nueva directiva a usuarios.

Para más información, consulte [New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy) y [Grant-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientPolicy) en la documentación del Shell de administración de Lync Server.


> [!NOTE]
> <UL>
> <LI>
> <P>De forma predeterminada, Lync Server 2013&nbsp;actualiza la configuración y las directivas de cliente cada tres horas.</P>
> <LI>
> <P>Si quiere seguir usando la configuración de directiva de grupo de versiones anteriores (como CustomStateURL), Lync 2013 identificará la configuración si se ubica en el nuevo subárbol de Registro de directiva (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync). No obstante, las directivas de cliente basadas en servidor tendrán precedencia.</P></LI></UL>


