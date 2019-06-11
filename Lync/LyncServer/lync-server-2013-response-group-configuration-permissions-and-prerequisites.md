---
title: 'Lync Server 2013: Permisos y requisitos previos de configuración de grupos de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1360a6dee8dbbf169fa0ceda1ee1b2f215ff09b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Permisos y requisitos previos de configuración de grupos de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

El grupo de respuesta es una característica de administración de llamadas de voz de empresa. En este tema se describe lo que debe tener en cuenta antes de poder configurar el grupo de respuesta y las credenciales administrativas y los permisos que necesita para realizar las tareas de configuración.

En esta sección se presupone que ha leído la documentación de planificación relacionada con el grupo de respuesta. Para obtener más información, consulte [planear las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) en la documentación de planeación.

<div>

## <a name="configuration-tools-and-administrative-roles"></a>Herramientas de configuración y roles administrativos

Puede usar las siguientes herramientas administrativas para configurar el grupo de respuesta:

  - Panel de control de Lync Server

  - Herramienta de configuración de grupo de respuesta

  - Shell de administración de Communications Server

Para configurar el grupo de respuesta, debe ser un miembro de al menos uno de los siguientes roles administrativos:


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Grupo de seguridad de Active Directory (1)</strong></p></td>
<td><p>Crear flujo de trabajo</p></td>
<td><p>Asignar administrador</p></td>
<td><p>Crear/asignar agentes, colas</p></td>
<td><p>Crear/administrar vacaciones y horas laborales</p></td>
<td><p>Activar/desactivar flujo de trabajo</p></td>
<td><p>Configurar flujo de trabajo (IVR o grupo de extensiones)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>√(2)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> un objeto de usuario de los servicios de dominio de Active Directory debe ser miembro del grupo de seguridad de Active Directory especificado de la lista. Un administrador u otro miembro delegado de un grupo de Active Directory con los permisos adecuados para agregar usuarios a un grupo de seguridad (por ejemplo, administrador, operadores de cuenta) debe agregar un objeto de usuario al grupo o grupo de seguridad de la lista para que el usuario pueda Realice las funciones de la lista. <STRONG>(2)</STRONG> solo para los flujos de trabajo que ha asignado el CsResponseGroupAdministrator a la CsResponseGroupManager. <STRONG>(3)</STRONG> un administrador de grupo de respuesta puede asignar otro miembro de CsResponseGroupManager a un flujo de trabajo que el administrador actual ya administra. <STRONG>(4)</STRONG> CsViewOnlyAdministrator solo puede ejecutar verbos de Shell de administración de Lync Server.



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>Requisitos previos de configuración del grupo de respuesta

El grupo de respuesta requiere los siguientes componentes:

  - Servicio de aplicaciones

  - Aplicación de grupo de respuesta

  - Paquetes de idioma

  - Almacén de archivos (para contener los archivos de audio)

  - Servicios web (incluye la herramienta de configuración de grupos de respuesta y la consola de inicio de sesión y cierre de sesión de los agentes)

Todos estos componentes se instalan de forma predeterminada al implementar la telefonía IP empresarial.

Es posible que tenga que realizar las siguientes tareas antes de configurar el grupo de respuesta:

  - Habilitar usuarios para Lync Server 2013 y Enterprise Voice.

  - Modificar un archivo de configuración para que sea compatible con estándares federales de procesamiento de información (FIPS).

  - Modificar la intercalación de base de datos para admitir caracteres Yi, Meng y Zang para nombres de cola y los nombres de grupo de agente.

<div>

## <a name="enabling-users"></a>Habilitar a los usuarios

El primer paso para configurar el grupo de respuesta es crear grupos de agentes. Antes de crear un grupo de agentes, debe habilitar los usuarios que serán agentes para el grupo de respuesta para Lync Server 2013 y Enterprise Voice. Habilitar usuarios para Lync Server 2013 suele ser un paso de la implementación del servidor Enterprise Edition o del servidor Standard Edition. Para obtener más información sobre cómo habilitar usuarios para Lync Server 2013, vea [deshabilitar o volver a habilitar la cuenta de usuario para Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Habilitar a los usuarios para Enterprise Voice suele ser un paso en la implementación de telefonía IP empresarial. Para obtener más información, consulte [Habilitar usuarios para telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

</div>

<div>

## <a name="complying-with-fips-requirements"></a>Cumplir con los requisitos de FIPS

Esta sección se le aplica solo si su organización necesita cumplir con estándares federales de procesamiento de información (FIPS).

Para cumplir los FIPS, debe modificar el archivo Web.config del nivel de aplicación para usar otro algoritmo de criptografía diferente después de instalar los servicios web. Debe especificar que ASP.NET use el algoritmo 3DES (Triple Data Encryption Standard) para procesar los datos de ver estado. Para la aplicación de grupo de respuesta, este requisito se aplica a la herramienta de configuración de grupos de respuesta y a la consola de inicio de sesión y de inicio de sesión del agente. Para obtener más información sobre este requisito, consulte el artículo 911722 de Microsoft Knowledge base, "puede recibir un mensaje de error al obtener acceso a ASP.NET páginas web que tengan habilitado ViewState después de la actualización de ASP.NET 1,1 [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)a ASP.net 2,0," en.

Para modificar el archivo Web.config, haga lo siguiente:

1.  En un editor de texto como Bloc de notas, abra el archivo Web.config de la aplicación.

2.  En el archivo Web. config, busque la `<system.web>` sección.

3.  Agregue la sección `<machineKey>` siguiente a la `<system.web>` sección:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Guarde el archivo Web.config.

5.  Reinicie el servicio de Internet Information Services (IIS) ejecutando el siguiente comando en un símbolo del sistema:
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Compatibilidad con caracteres Yi, Meng y Zang

Esta sección se le aplica solo si su organización necesita admitir caracteres Yi, Meng o Zang.

<div>


> [!NOTE]  
> Para obtener información sobre los caracteres Yi, Meng y Zang y por qué es posible que sean importantes para su implementación, vea la información de los conjuntos <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>de caracteres de GB18030.



</div>

Para admitir caracteres Yi, Meng o Zang, es necesario modificar la intercalación de la base de datos de Rgsconfig. Cambie la intercalación de la columna **Nombre** en las siguientes tablas de cada base de datos de Rgsconfig:

  - dbo.AgentGroups

  - dbo.BusinessHours

  - dbo.HolidaySets

  - dbo.Queues

  - dbo.Workflows

Para SQL Server 2008 R2 y SQL Server 2012, use la intercalación de Latín\_general\_100 (sensible a la tilde). Si usa esta intercalación, ningún nombre de objeto distingue entre mayúsculas y minúsculas.

Puede cambiar la intercalación con Microsoft SQL Server Management Studio. Para obtener más información sobre cómo usar esta herramienta, consulte "uso de SQL Server [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)Management Studio" en. Siga estos pasos para cambiar la intercalación:

1.  Asegúrese de que SQL Server Management Studio está configurado para permitir los cambios que requieren que las tablas se vuelvan a crear. Para obtener más información, vea "cuadro de diálogo Guardar (no permitido [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186))" en. Para obtener más información sobre cómo establecer una intercalación de columna, vea "Cómo: establecer la intercalación de columnas [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)(Visual Database Tools)" en.

2.  Use Microsoft SQL Server Management Studio para conectarse a la base de datos de Rgsconfig.

3.  Busque la tabla que desea cambiar en la base de datos de Rgsconfig, haga clic con el botón secundario en ella y, a continuación, haga clic en **Diseño**.

4.  Cambie la intercalación de la columna **Nombre** y guarde la tabla.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

