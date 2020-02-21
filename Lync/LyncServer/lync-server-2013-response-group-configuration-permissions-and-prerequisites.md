---
title: 'Lync Server 2013: permisos y requisitos previos de configuración del grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8e27d3495ce2152dee67a5f176c4a0d9f7e7f82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Permisos y requisitos previos de configuración de grupos de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

El grupo de respuesta es una característica de administración de llamadas de Enterprise Voice. Este tema describe lo que necesita preparar antes de poder configurar el grupo de respuesta, y los permisos y las credenciales administrativas que necesita para realizar tareas de configuración.

En esta sección, se da por supuesto que ha leído la documentación de planeación relacionada con el grupo de respuesta. Para obtener más información, consulte [planeación de las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) en la documentación referente a la planeación.

<div>

## <a name="configuration-tools-and-administrative-roles"></a>Herramientas de configuración y roles administrativos

Puede usar las siguientes herramientas administrativas para configurar el grupo de respuesta:

  - Panel de Control de Lync Server

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
<td><p>√ (2)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
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
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> un objeto de usuario de servicios de dominio de Active Directory debe ser miembro del grupo de seguridad de Active Directory especificado que aparece en la lista. Un administrador u otro miembro delegado de grupo de Active Directory con los permisos apropiados para agregar usuarios a un grupo de seguridad (por ejemplo, administrador, operadores de cuenta) deben agregar un objeto de usuario al grupo o grupo de seguridad de la lista para que el usuario pueda Realice las funciones enumeradas. <STRONG>(2)</STRONG> solo para flujos de trabajo que CsResponseGroupAdministrator ha asignado a la CsResponseGroupManager. <STRONG>(3)</STRONG> un administrador de grupo de respuesta puede asignar otro miembro de CsResponseGroupManager a un flujo de trabajo que el administrador actual ya administra. <STRONG>(4)</STRONG> CsViewOnlyAdministrator solo puede ejecutar los cmdlets "Get" del shell de administración de Lync Server.



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>Requisitos previos de configuración de grupos de respuesta

El grupo de respuesta requiere los siguientes componentes:

  - Servicio de aplicación

  - Aplicación de grupo de respuesta

  - Paquetes de idioma

  - Almacenamiento de archivos (para los archivos de audio)

  - Servicios web (incluye la herramienta de configuración de grupos de respuesta y la consola de inicio y cierre de sesión de los agentes)

Todos estos componentes se instalan de forma predeterminada al implementar Enterprise Voice.

Es posible que deba realizar las siguientes tareas antes de configurar el grupo de respuesta:

  - Habilitar usuarios para Lync Server 2013 y Enterprise Voice.

  - Modificar un archivo de configuración para que cumpla los Estándares federales de procesamiento de información (FIPS).

  - Modificar la intercalación de bases de datos para admitir caracteres Yi, Meng y Zang en los nombres de colas y los nombres de grupos de agentes.

<div>

## <a name="enabling-users"></a>Habilitar usuarios

El primer paso para configurar el grupo de respuesta es crear grupos de agentes. Antes de poder crear un grupo de agentes, debe habilitar los usuarios que van a ser agentes para el grupo de respuesta para Lync Server 2013 y Enterprise Voice. La habilitación de usuarios para Lync Server 2013 suele ser un paso en la implementación del servidor Enterprise Edition o del servidor Standard Edition. Para obtener más información sobre cómo habilitar usuarios para Lync Server 2013, vea [deshabilitar o volver a habilitar la cuenta de usuario para Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Habilitar usuarios en Enterprise Voice suele ser un paso de la implementación de Enterprise Voice. Para obtener más información, consulte [enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

</div>

<div>

## <a name="complying-with-fips-requirements"></a>Cumplimiento de los requisitos de FIPS

Solo debe tener en cuenta esta sección si su organización necesita cumplir los Estándares federales de procesamiento de información (FIPS).

Para cumplir los FIPS, modifique el archivo Web.config del nivel de aplicación para usar otro algoritmo de criptografía diferente después de instalar los servicios web. Especifique que ASP.NET usa el algoritmo Triple Data Encryption Standard (3DES) para procesar los datos de ver estado. Para la aplicación de grupo de respuesta, este requisito se aplica a la herramienta de configuración del grupo de respuesta y a la consola de inicio y cierre de sesión del agente. Para obtener más información acerca de este requisito, consulte el artículo 911722 de Microsoft Knowledge base, "puede recibir un mensaje de error cuando obtiene acceso a páginas web de ASP.NET que tienen habilitado ViewState después de la actualización de [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183)ASP.net 1,1 a ASP.net 2,0" en.

Para modificar el archivo Web.config:

1.  En un editor de texto, como el Bloc de notas, abra el archivo Web.config del nivel de aplicación.

2.  En el archivo Web. config, busque la `<system.web>` sección.

3.  Agregue la sección `<machineKey>` siguiente a en la `<system.web>` sección:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Guarde el archivo Web.config.

5.  Reinicie el servicio de Internet Information Services (IIS) ejecutando el siguiente comando en un símbolo del sistema:
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Compatibilidad con caracteres Yi, Meng y Zang

Solo debe tener en cuenta esta sección si su organización necesita admitir caracteres Yi, Meng o Zang.

<div>


> [!NOTE]  
> Para obtener información sobre los caracteres Yi, Meng y Zang y por qué son importantes para la implementación, consulte la información de los juegos <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A>de caracteres GB18030.



</div>

Para permitir la compatibilidad con caracteres Yi, Meng o Zang, debe modificar la intercalación de la base de datos de Rgsconfig. Cambie la intercalación de la columna **Nombre** en las siguientes tablas de cada base de datos de Rgsconfig:

  - DBO. AgentGroups

  - DBO. BusinessHours

  - DBO. HolidaySets

  - DBO. Colas

  - DBO. Flujos

Para SQL Server 2008 R2 y SQL Server 2012, use la intercalación de Latin\_general\_100 (sensible a la marca de acento). Si usa esta intercalación, los nombres de objetos no distinguirán entre mayúsculas y minúsculas.

Puede cambiar la intercalación usando Microsoft SQL Server Management Studio. Para obtener más información acerca del uso de esta herramienta, consulte "uso de SQL [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184)Server Management Studio" en. Siga estos pasos para cambiar la intercalación:

1.  Asegúrese de que SQL Server Management Studio está configurado para permitir los cambios que requieren que las tablas se vuelvan a crear. Para obtener más información, vea "cuadro de diálogo Guardar (no permitido [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186))" en. Para obtener información detallada sobre cómo establecer una intercalación de columna, vea "Cómo: establecer la intercalación de columnas [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185)(Visual Database Tools)" en.

2.  Usando Microsoft SQL Server Management Studio, conéctese a la base de datos de Rgsconfig.

3.  Busque la tabla que desee cambiar en la base de datos de Rgsconfig, haga clic con el botón secundario en la tabla y, a continuación, haga clic en **Diseñar**.

4.  Cambie la intercalación de la columna **Nombre** y guarde la tabla.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

