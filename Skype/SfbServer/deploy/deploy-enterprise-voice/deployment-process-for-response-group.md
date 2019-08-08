---
title: Proceso de implementación para un grupo de respuesta en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Proceso de implementación y pasos para el grupo respuesta de Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 12497d143f9ff5c7630f81db8f416e2f7c74d574
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233302"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Proceso de implementación para un grupo de respuesta en Skype empresarial

Proceso de implementación y pasos para el grupo respuesta de Skype empresarial Server Enterprise Voice.

El grupo de respuesta es una característica de voz de empresa que enruta y pone en cola las llamadas entrantes a grupos de personas, denominados agentes, como un servicio de asistencia o un servicio de asistencia al cliente.

Los componentes que requiere el grupo de respuesta se instalan y se habilitan automáticamente en el servidor front-end o el servidor Standard Edition al implementar la telefonía IP empresarial. Para que los usuarios puedan disponer de un grupo de respuesta, debe configurar grupos de agentes, después colas y, por último, flujos de trabajo. Además, un administrador de grupo de respuesta puede delegar la configuración de un flujo de trabajo existente a un administrador de grupo de respuesta, que podrá modificar y volver a configurar el flujo de trabajo y sus grupos de agentes y colas relacionados.

Para configurar el grupo de respuesta, debe ser un miembro de al menos uno de los siguientes roles administrativos:

|**Grupo de seguridad de Active Directory (1)** <br/> |Crear flujo de trabajo  <br/> |Asignar administrador  <br/> |Crear/asignar agentes, colas  <br/> |Crear/administrar vacaciones y horas laborales  <br/> |Activar/desactivar flujo de trabajo  <br/> |Configurar flujo de trabajo (IVR o grupo de extensiones)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√(2)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |

> [!NOTE]
> **(1)** un objeto de usuario de los servicios de dominio de Active Directory debe ser miembro del grupo de seguridad de Active Directory especificado de la lista. Un administrador u otro miembro delegado de un grupo de Active Directory con los permisos adecuados para agregar usuarios a un grupo de seguridad (por ejemplo, administrador, operadores de cuenta) debe agregar un objeto de usuario al grupo o grupo de seguridad de la lista para que el usuario pueda Realice las funciones de la lista. **(2)** solo para los flujos de trabajo que ha asignado el CsResponseGroupAdministrator a la CsResponseGroupManager. **(3)** un administrador de grupo de respuesta puede asignar otro miembro de CsResponseGroupManager a un flujo de trabajo que el administrador actual ya administra. **(4)** CsViewOnlyAdministrator solo puede ejecutar cmdlets "Get" de verbo.

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

### <a name="enabling-users"></a>Habilitar a los usuarios

El primer paso para configurar el grupo de respuesta es crear grupos de agentes. Antes de crear un grupo de agentes, debe habilitar los usuarios que serán agentes para el grupo de respuesta para Skype empresarial y telefonía IP empresarial. Habilitar a los usuarios para Skype empresarial normalmente es un paso de la implementación del servidor Enterprise Edition o del servidor Standard Edition. Para obtener más información sobre cómo habilitar usuarios para Skype empresarial, consulte [habilitar o deshabilitar usuarios para Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx). Habilitar a los usuarios para Enterprise Voice suele ser un paso en la implementación de telefonía IP empresarial. Para obtener más información, consulte [Habilitar usuarios para telefonía IP empresarial en Skype empresarial Server](enable-users-for-enterprise-voice.md).

### <a name="complying-with-fips-requirements"></a>Cumplir con los requisitos de FIPS

Esta sección se le aplica solo si su organización necesita cumplir con estándares federales de procesamiento de información (FIPS).

Para cumplir los FIPS, debe modificar el archivo Web.config del nivel de aplicación para usar otro algoritmo de criptografía diferente después de instalar los servicios web. Debe especificar que ASP.NET use el algoritmo 3DES (Triple Data Encryption Standard) para procesar los datos de ver estado. Para la aplicación de grupo de respuesta, este requisito se aplica a la herramienta de configuración de grupos de respuesta y a la consola de inicio de sesión y de inicio de sesión del agente. Para obtener más información sobre este requisito, consulte el artículo 911722 de Microsoft Knowledge base, "puede recibir un mensaje de error al obtener acceso a ASP.NET páginas web que tengan habilitado ViewState después de la actualización de ASP.NET 1,1 [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)a ASP.net 2,0," en.

Para modificar el archivo Web.config, haga lo siguiente:

1. En un editor de texto como Bloc de notas, abra el archivo Web.config de la aplicación.

2. En el archivo Web. config, busque la `<system.web>` sección.

3. Agregue la sección `<machineKey>` siguiente a la `<system.web>` sección:

   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Guarde el archivo Web.config.

5. Reinicie el servicio de Internet Information Services (IIS) ejecutando el siguiente comando en un símbolo del sistema:

   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Compatibilidad con caracteres Yi, Meng y Zang

Esta sección se le aplica solo si su organización necesita admitir caracteres Yi, Meng o Zang.

> [!NOTE]
> Para obtener información sobre los caracteres Yi, Meng y Zang y por qué es posible que sean importantes para su implementación, vea la información de los conjuntos [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223)de caracteres de GB18030.

Para admitir caracteres Yi, Meng o Zang, es necesario modificar la intercalación de la base de datos de Rgsconfig. Cambie la intercalación de la columna **Nombre** en las siguientes tablas de cada base de datos de Rgsconfig:

- dbo.AgentGroups

- dbo.BusinessHours

- dbo.HolidaySets

- dbo.Queues

- dbo.Workflows

Para SQL Server 2008 R2 y SQL Server 2012, use la intercalación Latin_General_100 (Acentos). Si usa esta intercalación, ningún nombre de objeto distingue entre mayúsculas y minúsculas.

Puede cambiar la intercalación con Microsoft SQL Server Management Studio. Para obtener más información sobre cómo usar esta herramienta, consulte ["uso de SQL Server Management Studio"](https://go.microsoft.com/fwlink/p/?linkId=196184). Siga estos pasos para cambiar la intercalación:

1. Asegúrese de que SQL Server Management Studio está configurado para permitir los cambios que requieren que las tablas se vuelvan a crear. Para obtener más información, vea ["cuadro de diálogo Guardar (no permitido)"](https://go.microsoft.com/fwlink/p/?linkId=196186). Para obtener más información sobre cómo establecer una intercalación de columna, vea en ["Cómo: establecer la intercalación de columnas (Visual Database Tools)"](https://go.microsoft.com/fwlink/p/?linkId=196185).

2. Use Microsoft SQL Server Management Studio para conectarse a la base de datos de Rgsconfig.

3. Busque la tabla que desea cambiar en la base de datos de Rgsconfig, haga clic con el botón secundario en ella y, a continuación, haga clic en **Diseño**.

4. Cambie la intercalación de la columna **Nombre** y guarde la tabla.

## <a name="response-group-deployment-steps"></a>Pasos de implementación del Grupo de respuesta

**Proceso de implementación de grupos de respuesta**

|**Fase**|**Pasos**|**Permisos**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Habilitar usuarios para Skype empresarial y para telefonía IP empresarial  <br/> |Habilitar usuarios que serán agentes de Skype empresarial y de telefonía IP empresarial. Estos usuarios necesitan estar habilitados para agregarlos a grupos de agentes. Normalmente, los usuarios están habilitados para Skype empresarial durante la implementación de servidor Standard Edition o Enterprise Edition. Los usuarios están habilitados para telefonía IP empresarial durante la implementación de telefonía IP empresarial.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Enable or Disable Users for Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Habilitar usuarios para telefonía IP empresarial en Skype empresarial Server](enable-users-for-enterprise-voice.md) <br/> |
|Crear y configurar grupos de respuesta formados por grupos de agentes, colas y flujos de trabajo  <br/> |1. Use el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial para hacer lo siguiente:  <br/> a. Crear y configurar grupos de respuesta  <br/> b. Crear y configurar colas  <br/> 2. opcionalmente, use el shell de administración de Skype empresarial para crear vacaciones y horas laborables de grupo de respuesta predefinidos.  <br/> 3. Use la herramienta de configuración de grupos de respuesta o el shell de administración de Skype empresarial para crear flujos de trabajo (grupos de captura o flujos de llamada de respuesta interactiva (IVR), incluidos los días laborables y festivos de grupo de respuesta personalizado.  <br/> Puede acceder a la herramienta de configuración de grupos de respuesta a través del panel de control de Skype empresarial Server.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> AdministradorGrupoRespuestaCs  <br/> |[Create Response Group Agent Groups](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Create Response Group Queues](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [Faculta Definir las horas de trabajo del grupo de respuesta en Skype empresarial](optional-define-response-group-business-hours.md) <br/> [Faculta Definir conjuntos de días festivos de grupos de respuesta en Skype empresarial](optional-define-response-group-holiday-sets.md) <br/> [Diseñar y crear flujos de trabajo de grupos de respuesta en Skype empresarial](designing-and-creating-response-group-workflows.md) <br/> |
|(Opcional) Personalizar la configuración de la aplicación  <br/> |Use el shell de administración de Skype empresarial Server para personalizar la configuración predeterminada de música en espera, el archivo de audio de música activa predeterminada, el período de gracia de timbre de timbre y la configuración de contexto de llamada.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Administración de la configuración de grupo de respuesta de nivel de aplicación en Skype empresarial](managing-application-level-response-group-settings.md) <br/> |
|(Opcional) Delegar la administración de los grupos de respuesta  <br/> |Asigne a los usuarios el rol CsResponseGroupManager para delegar la configuración de grupos de respuesta. Los administradores de grupos de respuesta pueden configurar los grupos de respuesta que tienen asignados.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planning for Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|Comprobar la implementación del grupo de respuesta  <br/> |Compruebe los mensajes de contestador automático del grupo de búsqueda y los flujos de trabajo de respuestas de voz interactiva para asegurarse de que la configuración funcione según lo previsto.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Resumen de escenarios de creación de flujo de trabajo

Al crear flujos de trabajo, hay dos posibles escenarios:

- **El Administrador crea y configura el flujo de trabajo**: el miembro del rol CsResponseGroupAdministrator (o equivalente) crea y activa el flujo de trabajo y todos los elementos del flujo de trabajo, como los grupos de agentes, colas, días festivos y horario laboral, música, en espera, etc.

- **El Administrador crea el flujo de trabajo y el Director configura las opciones**: el miembro del rol CsResponseGroupAdministrator (o equivalente) define el URI del SIP principal, Nombre para mostrar, asigna uno o varios miembros del rol CsResponseGroupManager, y selecciona una cola y activa el flujo de trabajo. El CsResponseGroupManager puede iniciar sesión a continuación y editar la configuración del flujo de trabajo creando grupos de agentes y también asigna el grupo a la cola, configurando el número de teléfono, horario laboral y festivos, música, en espera, etc.

    > [!NOTE]
    > Cuando desee crear un flujo de trabajo administrado, tiene que crear el flujo de trabajo como activo. Tras guardar un flujo de trabajo activo y administrado, modifique y desactive el flujo de trabajo.


