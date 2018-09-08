---
title: Proceso de implementación de grupo de respuesta en Skype para la empresa
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Proceso de implementación y los pasos para el grupo de respuesta en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 290db10e0a306217462015c43d9abb68e18ccb8a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884185"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Proceso de implementación de grupo de respuesta en Skype para la empresa

Proceso de implementación y los pasos para el grupo de respuesta en Skype para Business Server Enterprise Voice.

Grupo de respuesta es una característica de Enterprise Voice que enruta y pone en cola las llamadas entrantes a grupos de personas, denominados a agentes, como un servicio de asistencia o un departamento de servicio al cliente.

Los componentes que requiere el grupo de respuesta se instala y habilita automáticamente en el servidor Front-End o Standard Edition al implementar Enterprise Voice. Para que el grupo de respuesta esté disponible para los usuarios, debe configurar los flujos de trabajo, a continuación, las colas y, a continuación, grupos de agentes. Además, un administrador de grupo de respuesta puede delegar la configuración de un flujo de trabajo existente a un administrador de grupo de respuesta, que, a continuación, se puede modificar y volver a configurar el flujo de trabajo y sus grupos de agentes asociados y colas.

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
> **(1)** el objeto de usuario an Active Directory Domain Services debe ser un miembro del grupo de seguridad de Active Directory especificado que aparecen. Un administrador u otro miembro de grupo de Active Directory delegada con los permisos adecuados para agregar usuarios a un grupo de seguridad (por ejemplo, administrador, operadores de cuentas) debe agregar un objeto de usuario al grupo de seguridad enumerados o grupo para el usuario que puedan realizar las funciones enumeradas. **(2)** sólo para flujos de trabajo que ha asignado a la CsResponseGroupAdministrator a la CsResponseGroupManager. **(3)** un director de grupo de respuesta puede asignar a otro miembro de CsResponseGroupManager a un flujo de trabajo que ya administra el administrador actual. **(4)** CsViewOnlyAdministrator sólo puede ejecutar los cmdlets "Get" de verbo.

## <a name="response-group-configuration-prerequisites"></a>Requisitos previos de configuración de grupo de respuesta

Grupo de respuesta requiere los siguientes componentes:

- Servicio de aplicaciones

- Aplicación de grupo de respuesta

- Paquetes de idioma

- Almacén de archivos (para contener los archivos de audio)

- Servicios Web (incluye la herramienta de configuración de grupo de respuesta y la consola de inicio de sesión y cierre de sesión de los agentes)

Todos estos componentes se instalan de forma predeterminada al implementar Enterprise Voice.

Es posible que necesite realizar las siguientes tareas antes de configurar el grupo de respuesta:

- Permitir a los usuarios para Lync Server 2013 y Enterprise Voice.

- Modificar un archivo de configuración para que sea compatible con estándares federales de procesamiento de información (FIPS).

- Modificar la intercalación de base de datos para admitir caracteres Yi, Meng y Zang para nombres de cola y los nombres de grupo de agente.

### <a name="enabling-users"></a>Habilitar a los usuarios

El primer paso en la configuración de grupo de respuesta es para crear grupos de agentes. Antes de poder crear un grupo de agentes, debe habilitar a los usuarios que vayan a ser agentes para el grupo de respuesta de Skype para empresas y Enterprise Voice. Permitir a los usuarios de Skype para la empresa suele ser un paso en el servidor Enterprise Edition o la implementación de servidor Standard Edition. Para obtener información detallada acerca de cómo habilitar a los usuarios de Skype para la empresa, consulte [Enable or Disable Users for Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx). Habilitación de usuarios para Enterprise Voice normalmente es un paso en la implementación de Enterprise Voice. Para obtener información detallada, vea [Permitir a los usuarios para Enterprise Voice en Skype para Business Server](enable-users-for-enterprise-voice.md).

### <a name="complying-with-fips-requirements"></a>Cumplir con los requisitos de FIPS

Esta sección se le aplica solo si su organización necesita cumplir con estándares federales de procesamiento de información (FIPS).

Para cumplir los FIPS, debe modificar el archivo Web.config del nivel de aplicación para usar otro algoritmo de criptografía diferente después de instalar los servicios web. Debe especificar que ASP.NET use el algoritmo 3DES (Triple Data Encryption Standard) para procesar los datos de ver estado. Para la aplicación de grupo de respuesta, este requisito se aplica a la herramienta de configuración de grupo de respuesta y la consola de inicio de sesión y cierre de sesión del agente. Para obtener información detallada acerca de este requisito, vea el artículo de Microsoft Knowledge Base 911722, "puede recibir un mensaje de error cuando tenga acceso a las páginas Web ASP.NET que tienen habilitado después de actualizar desde ASP.NET 1.1 a ASP.NET 2.0, el estado de vista" en [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183).

Para modificar el archivo Web.config, haga lo siguiente:

1. En un editor de texto como Bloc de notas, abra el archivo Web.config de la aplicación.

2. En el archivo Web.config, busque la `<system.web>` sección.

3. Agregue el siguiente `<machineKey>` sección para en el `<system.web>` sección:

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
> Para obtener información sobre qué son los caracteres Yi, Meng y Zang y por qué puede ser importantes para la implementación, vea la información en los conjuntos de caracteres GB18030 [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223).

Para admitir caracteres Yi, Meng o Zang, es necesario modificar la intercalación de la base de datos de Rgsconfig. Cambie la intercalación de la columna **Nombre** en las siguientes tablas de cada base de datos de Rgsconfig:

- dbo. AgentGroups

- dbo. BusinessHours

- dbo. HolidaySets

- dbo. Colas

- dbo. Flujos de trabajo

Para SQL Server 2008 R2 y SQL Server 2012, use la Latin_General_100 (distinción de acentos) intercalación. Si usa esta intercalación, ningún nombre de objeto distingue entre mayúsculas y minúsculas.

Puede cambiar la intercalación con Microsoft SQL Server Management Studio. Para obtener información detallada sobre el uso de esta herramienta, vea ["uso de SQL Server Management Studio"](https://go.microsoft.com/fwlink/p/?linkId=196184). Siga estos pasos para cambiar la intercalación:

1. Asegúrese de que SQL Server Management Studio está configurado para permitir los cambios que requieren que las tablas se vuelvan a crear. Para obtener información detallada, vea ["Guardar (no permitido) cuadro de diálogo"](https://go.microsoft.com/fwlink/p/?linkId=196186). Para obtener información detallada sobre la configuración de una intercalación de columna, consulte en ["Cómo: Establecer intercalación de columna (Visual Database Tools)"](https://go.microsoft.com/fwlink/p/?linkId=196185).

2. Use Microsoft SQL Server Management Studio para conectarse a la base de datos de Rgsconfig.

3. Busque la tabla que desea cambiar en la base de datos de Rgsconfig, haga clic con el botón secundario en ella y, a continuación, haga clic en **Diseño**.

4. Cambie la intercalación de la columna **Nombre** y guarde la tabla.

## <a name="response-group-deployment-steps"></a>Pasos de implementación del Grupo de respuesta

**Proceso de implementación de grupos de respuesta**

|**Fase**|**Pasos**|**Permisos**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Permitir a que los usuarios de Skype para la empresa y para Enterprise Voice  <br/> |Permitir que los usuarios que vayan a ser agentes de Skype para empresas y Enterprise Voice. Estos usuarios necesitan estar habilitados para agregarlos a grupos de agentes. Normalmente, los usuarios están habilitados para Skype para la empresa durante la implementación de servidor Standard Edition o de Enterprise Edition. Los usuarios están habilitados para Enterprise Voice durante la implementación de Enterprise Voice.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Habilitar o deshabilitar usuarios para Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Habilitar a usuarios para Enterprise Voice en Skype para Business Server](enable-users-for-enterprise-voice.md) <br/> |
|Crear y configurar grupos de respuesta formados por grupos de agentes, colas y flujos de trabajo  <br/> |1. Utilice el Skype para Panel de Control de servidor empresarial o Skype para Shell de administración de servidor empresarial para hacer lo siguiente:  <br/> a. Crear y configurar grupos de respuesta  <br/> b. Crear y configurar colas  <br/> 2. de forma opcional, usar Skype para Shell de administración de servidor empresarial para crear respuesta predefinido horarios laborales de grupos y los días festivos.  <br/> 3. uso de la herramienta de configuración de grupo de respuesta o Skype para Shell de administración de servidor empresarial para crear flujos de trabajo (grupos de extensiones o flujos de llamadas de voz interactiva (IVR) de respuesta), incluidos el horarios laborales de grupos y los días festivos de respuesta.  <br/> Para tener acceso a la herramienta de configuración de grupo de respuesta a través de Skype para el Panel de Control de servidor empresarial.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Crear grupos de agentes del grupo de respuesta](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Crear colas de grupo de respuesta](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [(Opcional) Grupo de respuesta de definir el horario en Skype para la empresa](optional-define-response-group-business-hours.md) <br/> [(Opcional) Días festivos de definir grupo de respuesta se establecen en Skype para la empresa](optional-define-response-group-holiday-sets.md) <br/> [Diseñar y crear flujos de trabajo de grupo de respuesta en Skype para la empresa](designing-and-creating-response-group-workflows.md) <br/> |
|(Opcional) Personalizar la configuración de la aplicación  <br/> |Usar Skype para Shell de administración de servidor empresarial para personalizar la configuración de música en espera predeterminada, el archivo de audio de música en espera de forma predeterminada, el período de gracia de devolución de llamada de agente y la configuración del contexto de llamada.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Administración de la configuración de grupo de respuesta de nivel de la aplicación en Skype para la empresa](managing-application-level-response-group-settings.md) <br/> |
|(Opcional) Delegar la administración de los grupos de respuesta  <br/> |Asignar el rol CsResponseGroupManager para delegar la configuración de grupos de respuesta de los usuarios. Los administradores de grupo de respuesta, a continuación, pueden configurar los grupos de respuesta asignados a ellos.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planeación de Control de acceso basado en roles](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|Comprobar la implementación del grupo de respuesta  <br/> |Compruebe los mensajes de contestador automático del grupo de búsqueda y los flujos de trabajo de respuestas de voz interactiva para asegurarse de que la configuración funcione según lo previsto.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Resumen de escenarios de creación de flujo de trabajo

Al crear flujos de trabajo, hay dos posibles escenarios:

- **El Administrador crea y configura el flujo de trabajo**: el miembro del rol CsResponseGroupAdministrator (o equivalente) crea y activa el flujo de trabajo y todos los elementos del flujo de trabajo, como los grupos de agentes, colas, días festivos y horario laboral, música, en espera, etc.

- **El Administrador crea el flujo de trabajo y el Director configura las opciones**: el miembro del rol CsResponseGroupAdministrator (o equivalente) define el URI del SIP principal, Nombre para mostrar, asigna uno o varios miembros del rol CsResponseGroupManager, y selecciona una cola y activa el flujo de trabajo. El CsResponseGroupManager puede iniciar sesión a continuación y editar la configuración del flujo de trabajo creando grupos de agentes y también asigna el grupo a la cola, configurando el número de teléfono, horario laboral y festivos, música, en espera, etc.

    > [!NOTE]
    > Cuando desee crear un flujo de trabajo administrado, tiene que crear el flujo de trabajo como activo. Tras guardar un flujo de trabajo activo y administrado, modifique y desactive el flujo de trabajo.


