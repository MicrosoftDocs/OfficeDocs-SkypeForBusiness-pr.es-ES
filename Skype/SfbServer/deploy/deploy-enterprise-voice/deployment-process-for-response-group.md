---
title: Proceso de implementación del grupo de respuesta en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Proceso de implementación y pasos para el grupo de respuesta en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: cec795b5215caa81b281379cd4c433563ccebf83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812330"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Proceso de implementación del grupo de respuesta en Skype Empresarial

Proceso de implementación y pasos para el grupo de respuesta en Skype Empresarial Server Telefonía IP empresarial.

Grupo de respuesta es una Telefonía IP empresarial que enruta y pone en cola las llamadas entrantes a grupos de personas, llamados agentes, como un servicio de asistencia o un servicio de atención al cliente.

Los componentes que necesita el grupo de respuesta se instalan y se habilitan automáticamente en el servidor front-end o servidor Standard Edition al implementar Enterprise Voice. Para que el grupo de respuesta esté disponible para los usuarios, debe configurar los grupos de agentes; a continuación, las colas y, por último, los flujos de trabajo. Además, un administrador de grupo de respuesta puede delegar la configuración de un flujo de trabajo existente a un administrador de grupo de respuesta, que puede modificar y volver a configurar el flujo de trabajo y sus grupos de agentes y colas asociados.

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
> **(1) Un** objeto de usuario de Servicios de dominio de Active Directory debe ser miembro del grupo de seguridad de Active Directory especificado enumerado. Un administrador u otro miembro delegado del grupo de Active Directory con los permisos adecuados para agregar usuarios a un grupo de seguridad (por ejemplo, Administrador, Operadores de cuenta) debe agregar un objeto de usuario al grupo o grupo de seguridad enumerado para que el usuario pueda realizar las funciones enumeradas. **(2) Solo** para flujos de trabajo que CsResponseGroupAdministrator ha asignado a CsResponseGroupManager. **(3) Un** administrador de grupo de respuesta puede asignar otro miembro de CsResponseGroupManager a un flujo de trabajo que el administrador actual ya administra. **(4)** CsViewOnlyAdministrator solo puede ejecutar cmdlets de verbo "Get".

## <a name="response-group-configuration-prerequisites"></a>Requisitos previos de configuración de grupos de respuesta

El grupo de respuesta requiere los siguientes componentes:

- Servicio de aplicación

- Aplicación de grupo de respuesta

- Paquetes de idioma

- Almacenamiento de archivos (para los archivos de audio)

- Servicios web (incluye la Herramienta de configuración de grupo de respuesta y la consola de inicio y salida de los agentes)

Todos estos componentes se instalan de forma predeterminada al implementar Enterprise Voice.

Es posible que deba realizar las siguientes tareas antes de configurar el grupo de respuesta:

- Habilite a los usuarios para Lync Server 2013 y Telefonía IP empresarial.

- Modificar un archivo de configuración para que cumpla los Estándares federales de procesamiento de información (FIPS).

- Modificar la intercalación de bases de datos para admitir caracteres Yi, Meng y Zang en los nombres de colas y los nombres de grupos de agentes.

### <a name="enabling-users"></a>Habilitar usuarios

El primer paso para configurar el grupo de respuesta es crear grupos de agentes. Para poder crear un grupo de agentes, debe habilitar a los usuarios que serán agentes del grupo de respuesta para Skype Empresarial y Telefonía IP empresarial. La habilitación de usuarios para Skype Empresarial suele ser un paso en la implementación de servidores Enterprise Edition o Standard Edition. Para obtener más información sobre cómo habilitar usuarios para Skype Empresarial, consulte Habilitar o deshabilitar [usuarios para Lync Server 2013 Preview.](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) Habilitar usuarios en Enterprise Voice suele ser un paso de la implementación de Enterprise Voice. Para obtener más información, consulte [Habilitar usuarios para Telefonía IP empresarial en Skype Empresarial Server.](enable-users-for-enterprise-voice.md)

### <a name="complying-with-fips-requirements"></a>Cumplimiento de los requisitos de FIPS

Solo debe tener en cuenta esta sección si su organización necesita cumplir los Estándares federales de procesamiento de información (FIPS).

Para cumplir los FIPS, modifique el archivo Web.config del nivel de aplicación para usar otro algoritmo de criptografía diferente después de instalar los servicios web. Especifique que ASP.NET usa el algoritmo Triple Data Encryption Standard (3DES) para procesar los datos de ver estado. Para la aplicación Grupo de respuesta, este requisito se aplica a la Herramienta de configuración de grupo de respuesta y a la consola de inicio y salida del agente. Para obtener más información sobre este requisito, consulte el artículo 911722 de Microsoft Knowledge Base, "Es posible que reciba un mensaje de error al obtener acceso ASP.NET páginas web con ViewState habilitado después de actualizar de ASP.NET 1.1 ASP.NET 2.0", en [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183) .

Para modificar el archivo Web.config:

1. En un editor de texto, como el Bloc de notas, abra el archivo Web.config del nivel de aplicación.

2. En el Web.config, busque la  `<system.web>` sección.

3. Agregue la siguiente  `<machineKey>` sección a la `<system.web>` sección:

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Guarde el archivo Web.config.

5. Reinicie el servicio Internet Information Services (IIS) ejecutando el siguiente comando en un símbolo del sistema:

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Compatibilidad con caracteres Yi, Meng y Zang

Solo debe tener en cuenta esta sección si su organización necesita admitir caracteres Yi, Meng o Zang.

> [!NOTE]
> Para obtener información sobre los caracteres Yi, Meng y Zang y por qué pueden ser importantes para su implementación, vea la información sobre los juegos de caracteres GB18030 [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223) .

Para permitir la compatibilidad con caracteres Yi, Meng o Zang, debe modificar la intercalación de la base de datos de Rgsconfig. Cambie la intercalación de la columna **Nombre** en las siguientes tablas de cada base de datos de Rgsconfig:

- dbo. AgentGroups

- dbo. BusinessHours

- dbo. HolidaySets

- dbo. Colas

- dbo. Flujos de trabajo

Para SQL Server 2008 R2 y SQL Server 2012, use la intercalación Latin_General_100 (distingue acentos). Si usa esta intercalación, los nombres de objetos no distinguirán entre mayúsculas y minúsculas.

Puede cambiar la intercalación usando Microsoft SQL Server Management Studio. Para obtener más información sobre el uso de esta herramienta, consulte ["Uso SQL Server Management Studio".](https://go.microsoft.com/fwlink/p/?linkId=196184) Siga estos pasos para cambiar la intercalación:

1. Asegúrese de que SQL Server Management Studio está configurado para permitir los cambios que requieren que las tablas se vuelvan a crear. Para obtener más información, vea "Cuadro de diálogo [Guardar (no permitido)".](https://go.microsoft.com/fwlink/p/?linkId=196186) Para obtener más información acerca de cómo establecer una intercalación de columnas, consulte ["How to: Set Column Collation (Visual Database Tools)"](https://go.microsoft.com/fwlink/p/?linkId=196185).

2. Usando Microsoft SQL Server Management Studio, conéctese a la base de datos de Rgsconfig.

3. Busque la tabla que desee cambiar en la base de datos de Rgsconfig, haga clic con el botón secundario en la tabla y, a continuación, haga clic en **Diseñar**.

4. Cambie la intercalación de la columna **Nombre** y guarde la tabla.

## <a name="response-group-deployment-steps"></a>Pasos de implementación del grupo de respuesta

**Proceso de implementación de grupos de respuesta**

|**Fase**|**Pasos**|**Permisos**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Habilitar usuarios para Skype Empresarial y para Telefonía IP empresarial  <br/> |Habilite a los usuarios que serán agentes de Skype Empresarial y Telefonía IP empresarial. Los usuarios deben estar habilitados antes de poder agregarlos a grupos de agentes. Normalmente, los usuarios están habilitados para Skype Empresarial durante la implementación del servidor Enterprise Edition o Standard Edition. Los usuarios están habilitados para Telefonía IP empresarial durante la Telefonía IP empresarial implementación.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Habilitar o deshabilitar usuarios para Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Habilitar usuarios para Telefonía IP empresarial en Skype Empresarial Server](enable-users-for-enterprise-voice.md) <br/> |
|Creación y configuración de grupos de respuesta formados por grupos de agentes, colas y flujos de trabajo  <br/> |1. Use el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server para hacer lo siguiente:  <br/> a. Crear y configurar grupos de respuesta  <br/> b. Crear y configurar colas  <br/> 2. Opcionalmente, use el Shell de administración de Skype Empresarial Server para crear horarios laborales y días festivos de grupos de respuesta predefinidos.  <br/> 3. Use la Herramienta de configuración de grupo de respuesta o el Shell de administración de Skype Empresarial Server para crear flujos de trabajo (grupos de extensiones o flujos de llamadas de respuesta interactiva de voz (IVR), incluidos el horario laboral y los días festivos del grupo de respuesta personalizado.  <br/> Puede obtener acceso a la Herramienta de configuración de grupo de respuesta a través del Panel de control de Skype Empresarial Server.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Crear grupos de agentes de grupos de respuesta](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Crear colas de grupo de respuesta](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [(Opcional) Definir el horario comercial del grupo de respuesta en Skype Empresarial](optional-define-response-group-business-hours.md) <br/> [(Opcional) Definir conjuntos de días festivos de grupo de respuesta en Skype Empresarial](optional-define-response-group-holiday-sets.md) <br/> [Diseño y creación de flujos de trabajo de grupo de respuesta en Skype Empresarial](designing-and-creating-response-group-workflows.md) <br/> |
|(Opcional) Personalización de la configuración de nivel de aplicación  <br/> |Use el Shell de administración de Skype Empresarial Server para personalizar la configuración de música en espera predeterminada, el archivo de audio de música en espera predeterminado, el período de gracia de devolución de llamada del agente y la configuración del contexto de llamada.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Administración de la configuración del grupo de respuesta en el nivel de aplicación en Skype Empresarial](managing-application-level-response-group-settings.md) <br/> |
|(Opcional) Delegación de la administración de los grupos de respuesta  <br/> |Asigne a los usuarios el rol CsResponseGroupManager para delegar la configuración de grupos de respuesta. A continuación, los administradores de grupos de respuesta pueden configurar los grupos de respuesta que se les han asignado.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planeación del control de acceso basado en roles](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|Comprobación del grupo de respuesta  <br/> |Compruebe los mensajes de contestador automático del grupo de búsqueda y los flujos de trabajo de respuestas de voz interactiva para asegurarse de que la configuración funcione según lo previsto.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Introducción a los escenarios de creación de flujos de trabajo

Al crear flujos de trabajo, hay dos posibles escenarios:

- **El Administrador crea y configura el flujo de trabajo**: el miembro del rol CsResponseGroupAdministrator (o equivalente) crea y activa el flujo de trabajo y todos los elementos del flujo de trabajo, como los grupos de agentes, colas, días festivos y horario laboral, música, en espera, etc.

- **El Administrador crea el flujo de trabajo y el Director configura las opciones**: el miembro del rol CsResponseGroupAdministrator (o equivalente) define el URI del SIP principal, Nombre para mostrar, asigna uno o varios miembros del rol CsResponseGroupManager, y selecciona una cola y activa el flujo de trabajo. El CsResponseGroupManager puede iniciar sesión a continuación y editar la configuración del flujo de trabajo creando grupos de agentes y también asigna el grupo a la cola, configurando el número de teléfono, horario laboral y festivos, música, en espera, etc.

    > [!NOTE]
    > Cuando desee crear un flujo de trabajo administrado, tiene que crear el flujo de trabajo como activo. Tras guardar un flujo de trabajo activo y administrado, modifique y desactive el flujo de trabajo.


