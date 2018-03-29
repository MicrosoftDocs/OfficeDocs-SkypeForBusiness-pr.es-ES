---
title: Proceso de implementación de grupos de respuesta en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Proceso de implementación y los pasos para el grupo de respuesta en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: ca390f19b98921f6c8d7fa2a02c8e5065e605a94
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-for-response-group-in-skype-for-business-2015"></a>Proceso de implementación de grupos de respuesta en Skype Empresarial 2015
 
Proceso de implementación y los pasos para el grupo de respuesta en Skype para Telefonía IP empresarial de Business Server.
  
Grupo de respuesta es una característica de Telefonía IP empresarial que dirige y pone en cola las llamadas entrantes a grupos de personas, denominados a agentes, como un departamento de soporte o un servicio de asistencia al cliente.
  
Los componentes que requiere el grupo de respuesta instalados y habilitados automáticamente en el servidor Standard Edition o de servidor Front-End al implementar la Telefonía IP empresarial. Para que el grupo de respuesta disponibles para los usuarios, debe configurar flujos de trabajo, a continuación, las colas y, a continuación, grupos de agentes. Además, un administrador de grupo de respuesta puede delegar la configuración de un flujo de trabajo existente a un administrador de grupo respuesta, que después puede modificar y volver a configurar el flujo de trabajo y sus grupos de agentes asociados y colas.
  
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
> **(1)** el objeto de usuario de servicios un dominio de Active Directory debe ser miembro del grupo de seguridad de Active Directory especificado enumerados. Un administrador u otro miembro de grupo de Active Directory delegada con los permisos adecuados para agregar usuarios a un grupo de seguridad (por ejemplo, administrador, operadores de cuentas) debe agregar un objeto de usuario al grupo de seguridad enumerados o grupo para el usuario para poder realizar las funciones enumeradas. **(2)** sólo para flujos de trabajo que tiene asignados el CsResponseGroupAdministrator el CsResponseGroupManager. **(3)** el Administrador de grupo de respuesta A puede asignar a otro miembro de CsResponseGroupManager un flujo de trabajo que ya administra el administrador actual. **(4)** CsViewOnlyAdministrator sólo puede ejecutar cmdlets de verbo "Get".
  
## <a name="response-group-configuration-prerequisites"></a>Requisitos previos de configuración de grupo de respuesta

Grupo de respuesta requiere los siguientes componentes:
  
- Servicio de aplicaciones
    
- Aplicación de grupo de respuesta
    
- Paquetes de idioma
    
- Almacén de archivos (para contener los archivos de audio)
    
- Servicios Web (que incluye la herramienta de configuración de grupo de respuesta y la consola de inicio de sesión y cierre de sesión de los agentes)
    
Todos estos componentes se instalan de forma predeterminada al implementar la Telefonía IP empresarial.
  
Debe realizar las siguientes tareas antes de configurar el grupo de respuesta:
  
- Habilitar a usuarios para Lync Server 2013 y Telefonía IP empresarial.
    
- Modificar un archivo de configuración para que sea compatible con estándares federales de procesamiento de información (FIPS).
    
- Modificar la intercalación de base de datos para admitir caracteres Yi, Meng y Zang para nombres de cola y los nombres de grupo de agente.
    
### <a name="enabling-users"></a>Habilitar a los usuarios

El primer paso para configurar el grupo de respuesta consiste en crear a agente de grupos. Para poder crear un grupo de agentes, debe habilitar a los usuarios que vayan a ser agentes para el grupo de respuesta de Skype para empresas y Telefonía IP empresarial. Permitir a los usuarios de Skype para el negocio suele ser un paso en el servidor Enterprise Edition o la implementación del servidor Standard Edition. Para obtener más información acerca de cómo habilitar los usuarios de Skype para empresas, vea [Habilitar o deshabilitar usuarios para Lync Server 2013 Preview](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx). Permitir a los usuarios de Telefonía IP empresarial suele ser un paso en la implementación de Telefonía IP empresarial. Para obtener información detallada, vea [Permitir a los usuarios de Telefonía IP empresarial en Skype para Business Server 2015](enable-users-for-enterprise-voice.md). 
  
### <a name="complying-with-fips-requirements"></a>Cumplir con los requisitos de FIPS

Esta sección se le aplica solo si su organización necesita cumplir con estándares federales de procesamiento de información (FIPS).
  
Para cumplir los FIPS, debe modificar el archivo Web.config del nivel de aplicación para usar otro algoritmo de criptografía diferente después de instalar los servicios web. Debe especificar que ASP.NET use el algoritmo 3DES (Triple Data Encryption Standard) para procesar los datos de ver estado. Para la aplicación de grupo de respuesta, este requisito se aplica a la herramienta de configuración de grupo de respuesta y la consola de inicio de sesión y cierre de sesión del agente. Para obtener detalles acerca de este requisito, consulte el artículo de Microsoft Knowledge Base 911722, "puede aparecer un mensaje de error cuando tenga acceso a las páginas Web ASP.NET que tienen la opción ViewState habilitada después de actualizar desde ASP.NET 1.1 a ASP.NET 2.0" en [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183).
  
Para modificar el archivo Web.config, haga lo siguiente:
  
1. En un editor de texto como Bloc de notas, abra el archivo Web.config de la aplicación.
    
2. En el archivo Web.config, busque la `<system.web>` sección.
    
3. Agregue el siguiente `<machineKey>` sección a en el `<system.web>` sección:
    
   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Guarde el archivo Web.config.
    
5. Reinicie el servicio servicios de Internet Information Server (IIS) ejecutando el siguiente comando en un símbolo del sistema: 
    
   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Compatibilidad con caracteres Yi, Meng y Zang

Esta sección se le aplica solo si su organización necesita admitir caracteres Yi, Meng o Zang.
  
> [!NOTE]
> Para obtener información sobre qué son los caracteres Yi Meng y Zang y por qué puede ser importantes para su implementación, vea la información sobre los juegos de caracteres GB18030 [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223). 
  
Para admitir caracteres Yi, Meng o Zang, es necesario modificar la intercalación de la base de datos de Rgsconfig. Cambie la intercalación de la columna **Nombre** en las siguientes tablas de cada base de datos de Rgsconfig:
  
- dbo. AgentGroups
    
- dbo. BusinessHours
    
- dbo. HolidaySets
    
- dbo. Colas de trabajos
    
- dbo. Flujos de trabajo
    
Para SQL Server 2008 R2 y uso el Latin_General_100 (acentos) intercalación de SQL Server 2012. Si usa esta intercalación, ningún nombre de objeto distingue entre mayúsculas y minúsculas.
  
Puede cambiar la intercalación con Microsoft SQL Server Management Studio. Para obtener más información acerca del uso de esta herramienta, consulte ["utilizar SQL Server Management Studio"](https://go.microsoft.com/fwlink/p/?linkId=196184). Siga estos pasos para cambiar la intercalación:
  
1. Asegúrese de que SQL Server Management Studio está configurado para permitir los cambios que requieren que las tablas se vuelvan a crear. Para obtener más información, consulte ["(no permitido) de guardar cuadro de diálogo"](https://go.microsoft.com/fwlink/p/?linkId=196186). Para obtener más información acerca de la configuración de intercalación de columna, consulte en ["Cómo: conjunto de intercalación de columnas (Visual Database Tools)"](https://go.microsoft.com/fwlink/p/?linkId=196185).
    
2. Use Microsoft SQL Server Management Studio para conectarse a la base de datos de Rgsconfig.
    
3. Busque la tabla que desea cambiar en la base de datos de Rgsconfig, haga clic con el botón secundario en ella y, a continuación, haga clic en **Diseño**. 
    
4. Cambie la intercalación de la columna **Nombre** y guarde la tabla.
    
## <a name="response-group-deployment-steps"></a>Pasos de implementación del Grupo de respuesta

**Proceso de implementación de grupo de respuesta**

|**Fase**|**Pasos**|**Permisos**|**Documentación sobre la implementación**|
|:-----|:-----|:-----|:-----|
|Habilitar a usuarios de Skype para empresas y para la Telefonía IP empresarial  <br/> |Permitir a los usuarios que vayan a ser agentes de Skype para empresas y Telefonía IP empresarial. Estos usuarios necesitan estar habilitados para agregarlos a grupos de agentes. Normalmente, los usuarios están habilitados para Skype para el negocio durante la implementación de Standard Edition server o la Enterprise Edition. Los usuarios están habilitados para Telefonía IP empresarial durante la implementación de Telefonía IP empresarial.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Habilitar o deshabilitar usuarios para Lync Server 2013 Preview](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Permitir que los usuarios de Telefonía IP empresarial en Skype para Business Server 2015](enable-users-for-enterprise-voice.md) <br/> |
|Crear y configurar grupos de respuesta formados por grupos de agentes, colas y flujos de trabajo  <br/> |1. Utilice el Skype para Business Server Control Panel o Skype para negocios de Shell de administración de servidor para hacer lo siguiente:  <br/> a. Crear y configurar grupos de respuesta  <br/> b. Crear y configurar colas  <br/> 2. opcionalmente, utilizar Skype para negocios de Shell de administración de servidor para crear respuesta predefinida grupo horario y días festivos.  <br/> 3. use la herramienta de configuración de grupo de respuesta o Skype para negocios de Shell de administración de servidor para crear flujos de trabajo (grupos de captura o flujos de voz interactiva (IVR) de respuesta llamada), incluida la respuesta personalizada grupo horario y días festivos.  <br/> Para tener acceso a la herramienta de configuración de grupo de respuesta a través de Skype para el Panel de Control de servidor empresarial.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Crear grupos de agentes del grupo de respuesta](http://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Crear colas de respuesta grupo](http://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [(Opcional) Definir respuesta grupo horario en Skype para negocios 2015](optional-define-response-group-business-hours.md) <br/> [(Opcional) Definir grupo de respuesta festividades en Skype para negocios 2015](optional-define-response-group-holiday-sets.md) <br/> [Diseñar y crear flujos de trabajo de grupo de respuesta en Skype para negocios 2015](designing-and-creating-response-group-workflows.md) <br/> |
|(Opcional) Personalizar la configuración de la aplicación  <br/> |Usar Skype para negocios de Shell de administración de servidor para personalizar la configuración de música en espera de forma predeterminada, el archivo de audio de música en espera de forma predeterminada, el período de gracia de timbre de agente y la configuración del contexto de llamada.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Administración de la configuración de grupo de respuesta de nivel de aplicación en Skype para negocios 2015](managing-application-level-response-group-settings.md) <br/> |
|(Opcional) Delegar la administración de los grupos de respuesta  <br/> |Asignar la función de CsResponseGroupManager para delegar la configuración de grupos de respuesta de los usuarios. Los jefes de grupo de respuesta pueden configurar los grupos de respuesta asignados a ellos.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planning for Role-Based Access Control](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|Comprobar la implementación del grupo de respuesta  <br/> |Compruebe los mensajes de contestador automático del grupo de búsqueda y los flujos de trabajo de respuestas de voz interactiva para asegurarse de que la configuración funcione según lo previsto.  <br/> |-  <br/> |-  <br/> |
   
## <a name="overview-of-workflow-creation-scenarios"></a>Resumen de escenarios de creación de flujo de trabajo

Al crear flujos de trabajo, hay dos posibles escenarios:
  
- **El Administrador crea y configura el flujo de trabajo**: el miembro del rol CsResponseGroupAdministrator (o equivalente) crea y activa el flujo de trabajo y todos los elementos del flujo de trabajo, como los grupos de agentes, colas, días festivos y horario laboral, música, en espera, etc.
    
- **El Administrador crea el flujo de trabajo y el Director configura las opciones**: el miembro del rol CsResponseGroupAdministrator (o equivalente) define el URI del SIP principal, Nombre para mostrar, asigna uno o varios miembros del rol CsResponseGroupManager, y selecciona una cola y activa el flujo de trabajo. El CsResponseGroupManager puede iniciar sesión a continuación y editar la configuración del flujo de trabajo creando grupos de agentes y también asigna el grupo a la cola, configurando el número de teléfono, horario laboral y festivos, música, en espera, etc.
    
    > [!NOTE]
    > Cuando desee crear un flujo de trabajo administrado, tiene que crear el flujo de trabajo como activo. Tras guardar un flujo de trabajo activo y administrado, modifique y desactive el flujo de trabajo. 
  

