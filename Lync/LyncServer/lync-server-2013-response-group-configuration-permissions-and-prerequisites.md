---
title: "Lync Server 2013: Permisos y requisitos previos de config. de grupos de respuesta"
TOCTitle: Permisos y requisitos previos de configuración de grupos de respuesta
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48275046
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Permisos y requisitos previos de configuración de grupos de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Grupo de respuesta es una Telefonía IP empresarial de la característica de administración de llamadas. Este tema describe lo que necesita preparar antes de poder configurar Grupo de respuesta y los permisos y las credenciales administrativas necesarios para realizar tareas de configuración.

En esta sección se supone que ha leído la documentación sobre planificación relacionada con el Grupo de respuesta. Para más información, vea [Planificar las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) en la documentación sobre planificación.

## Herramientas de configuración y roles administrativos

Puede usar las siguientes herramientas administrativas para configurar el Grupo de respuesta:

  - Panel de control de Lync Server

  - Herramienta de configuración de grupo de respuesta

  - Shell de administración de Lync Server

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
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>v(2)</p></td>
<td><p>v(3)</p></td>
<td><p>v(3)</p></td>
<td><p>v(3)</p></td>
<td><p>v(3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <STRONG>(1)</STRONG> Un objeto de usuario de Servicios de dominio de Active Directory debe pertenecer al grupo de seguridad especificado de Active Directory que aparece en la lista. Un administrador u otro miembro de grupo de Active Directory delegado con permisos adecuados para agregar usuarios a un grupo de seguridad (por ejemplo, un administrador u operadores de cuenta) debe agregar un objeto de usuario al grupo de seguridad o al grupo indicado para que el usuario pueda realizar las funciones especificadas. <STRONG>(2)</STRONG> Solo para flujos de trabajo que CsResponseGroupAdministrator ha asignado a CsResponseGroupManager. <STRONG>(3)</STRONG> Un director del Grupo de respuesta puede asignar otro miembro de CsResponseGroupManager a un flujo de trabajo que el administrador actual ya administre. <STRONG>(4)</STRONG> CsViewOnlyAdministrator solo puede ejecutar cmdlets de Shell de administración de Lync Server en que aparezca el verbo "Get".



## Requisitos previos de configuración de Grupo de respuesta

Grupo de respuesta requiere los siguientes componentes:

  - Servicio de aplicaciones

  - Aplicación de grupo de respuesta

  - Paquetes de idioma

  - Almacén de archivos (para contener los archivos de audio)

  - Servicios web (incluye la Herramienta de configuración de grupo de respuesta y la consola de inicio y de cierre de sesión de los agentes)

Todos estos componentes se instalan de forma predeterminada cuando se implementa Telefonía IP empresarial.

Es posible que deba realizar las siguientes tareas antes de configurar Grupo de respuesta:

  - Habilitar a los usuarios de Lync Server 2013 y Telefonía IP empresarial.

  - Modificar un archivo de configuración para que sea compatible con estándares federales de procesamiento de información (FIPS).

  - Modificar la intercalación de base de datos para admitir caracteres Yi, Meng y Zang para nombres de cola y los nombres de grupo de agente.

## Habilitar a los usuarios

El primer paso para configurar el Grupo de respuesta es crear a grupos de agentes. Antes de poder crear un grupo de agentes, es necesario habilitar a los usuarios que serán agentes de los Grupo de respuesta para Lync Server 2013 y Telefonía IP empresarial. La habilitación de los usuarios para Lync Server 2013 suele ser un paso en la implementación del servidor Enterprise Edition o Standard Edition. Para información sobre cómo habilitar a los usuarios para Lync Server 2013, vea [Deshabilitación o rehabilitación de la cuenta de usuario de Lync Server en Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Habilitar a usuarios para Telefonía IP empresarial suele ser un paso en la implementación de Telefonía IP empresarial. Para más información, vea [Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

## Cumplir con los requisitos de FIPS

Esta sección se le aplica solo si su organización necesita cumplir con estándares federales de procesamiento de información (FIPS).

Para cumplir los FIPS, debe modificar el archivo Web.config del nivel de aplicación para usar otro algoritmo de criptografía diferente después de instalar los servicios web. Debe especificar que ASP.NET usa el algoritmo 3DES (Triple Data Encryption Standard) para procesar los datos de ver estado. En Aplicación de grupo de respuesta, este requisito se aplica a la consola de inicio y cierre de sesión de agentes y Herramienta de configuración de grupo de respuesta. Para ver más detalles sobre este requisito, consulte el artículo 911722 de Microsoft Knowledge Base, que explica que puede recibir un mensaje de error al acceder a las páginas web de ASP.NET con ViewState habilitado tras actualizar de ASP.NET 1.1 a ASP.NET 2.0, en [http://go.microsoft.com/fwlink/?linkid=196183\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=196183%26clcid=0xc0a).

Para modificar el archivo Web.config, haga lo siguiente:

1.  En un editor de texto como Bloc de notas, abra el archivo Web.config de la aplicación.

2.  En el archivo Web.config, busque la sección `<system.web>`.

3.  Agregue la siguiente sección `<machineKey>` a la sección `<system.web>`:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Guarde el archivo Web.config.

5.  Reinicie el servicio de Servicios de Internet Information Server (IIS) ejecutando el comando siguiente en un símbolo del sistema:
    
        iisreset

## Compatibilidad con caracteres Yi, Meng y Zang

Esta sección se le aplica solo si su organización necesita admitir caracteres Yi, Meng o Zang.


> [!NOTE]
> Para más información sobre qué son los caracteres Yi Meng y Zang y por qué pueden ser importantes para su implementación, vea la información sobre los conjuntos de caracteres GB18030 <A href="http://go.microsoft.com/fwlink/?linkid=240223%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=240223&amp;clcid=0xC0A</A>.



Para admitir caracteres Yi, Meng o Zang, es necesario modificar la intercalación de la base de datos de Rgsconfig. Cambie la intercalación de la columna **Nombre** en las siguientes tablas de cada base de datos de Rgsconfig:

  - dbo.AgentGroups

  - dbo.BusinessHours

  - dbo.HolidaySets

  - dbo.Queues

  - dbo.Workflows

Para SQL Server 2008 R2 y SQL Server 2012, use la intercalación Latin\_General\_100 (distingue acentos). Si usa esta intercalación, ningún nombre de objeto distingue entre mayúsculas y minúsculas.

Puede cambiar la intercalación con Microsoft SQL Server Management Studio. Para más información sobre cómo usar esta herramienta, vea "Uso de SQL Server Management Studio" en [http://go.microsoft.com/fwlink/p/?linkId=196184com/fwlink/?linkid=196184\&clcid=0xC0A](http://go.microsoft.com/fwlink/p/?linkid=196184com/fwlink/?linkid=196184%26clcid=0xc0a). Siga estos pasos para cambiar la intercalación:

1.  Asegúrese de que SQL Server Management Studio está configurado para permitir los cambios que requieren que las tablas se vuelvan a crear. Para más información, vea "Guardar (no permitido) cuadro de diálogo" en [http://go.microsoft.com/fwlink/?linkid=196186\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=196186%26clcid=0xc0a). Para más información sobre cómo establecer una intercalación de columna, vea "Cómo establecer la intercalación de columnas (Visual Database Tools)" en [http://go.microsoft.com/fwlink/?linkid=196185\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=196185%26clcid=0xc0a).

2.  con Microsoft SQL Server Management Studio, conéctese a la base de datos de Rgsconfig.

3.  Busque la tabla que desea cambiar en la base de datos de Rgsconfig, haga clic con el botón secundario en ella y haga clic en **Diseño**.

4.  Cambie la intercalación de la columna **Nombre** y guarde la tabla.

