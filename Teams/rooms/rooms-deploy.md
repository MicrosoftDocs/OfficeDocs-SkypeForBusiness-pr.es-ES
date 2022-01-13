---
title: Implementar Salas de Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lea este artículo para obtener información sobre cómo implementar Salas de Microsoft Teams, incluidas las fases de implementación.
ms.openlocfilehash: 1f9edd4ccd2c0de00c91b99cef4f3f27b081b9ab
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015240"
---
# <a name="deployment-overview"></a>Introducción general a la implementación

La implementación Salas de Microsoft Teams básicamente se divide en fases:

- Confirmar que las ubicaciones de implementación (espacios) cumplen las dependencias de implementación
- Crear Microsoft Teams o Skype Empresarial y Exchange cuentas y asignarlas a Salas de Teams (consulte Configurar cuentas [para Salas de Microsoft Teams)](rooms-configure-accounts.md)
- (Opcional) Configurar Azure Monitor para sus sistemas (consulte [Implementar Salas de Microsoft Teams administración con Azure Monitor](azure-monitor-deploy.md)
- Configurar Salas de Teams espacios de reunión y conectar los dispositivos periféricos que necesita (consulte la documentación oem para su conjunto de dispositivos)

## <a name="site-readiness"></a>Preparación del sitio 

Mientras los dispositivos ordenados se entregan a su organización, trabaje con sus equipos de redes, instalaciones y AV para asegurarse de que se cumplen las dependencias de implementación y que cada sitio y espacio está listo en términos de potencia, redes y pantalla. Además, asegúrese de que se cumplen los requisitos de instalación física. Para las consideraciones de instalación física, consulte con su proveedor y aproveche la experiencia de su equipo de AV al instalar y montar pantallas y ejecutar cableado.

Puede obtener más información sobre estas dependencias en los siguientes vínculos de orientación de planeación:

-   [Comprobar la disponibilidad de red](rooms-prep.md#check-network-availability)
-   [Certificados](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Pro sugerencia:** si debe usar servidores proxy para proporcionar acceso a Teams, primero [revise este artículo.](../proxy-servers-for-skype-for-business-online.md) Cuando se trata de Microsoft Teams multimedia en tiempo real a través de servidores proxy, se recomienda omitir los servidores proxy por completo. Microsoft Teams tráfico ya está cifrado, por lo que los servidores proxy no lo hacen más seguro y agregan latencia al tráfico en tiempo real. Como parte de su implementación más amplia, le recomendamos que siga las instrucciones de Preparar la red para [Teams](../prepare-network.md) para la planificación del ancho de banda y la evaluación de la idoneidad de su red para el tráfico en tiempo real.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![confirmar sitios.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Confirme que los sitios cumplen los requisitos clave para Salas de Microsoft Teams.</li><li>Confirme que ha proporcionado ancho de banda suficiente para cada sitio.</li></ul>| 
| ![planear la implementación de dispositivos.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empiece a planear la configuración y la implementación del dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Preparación del servicio

Para prepararse para su Salas de Microsoft Teams, realice las siguientes tareas centrales clave:

-   Definir Salas de Microsoft Teams de recursos.
-   Si se une Teams Sala Azure Active Directory, prepare un grupo de Azure AD con pertenencia dinámica para mantener todas las Salas de Teams de recursos. Esto simplificará la administración futura, como aplicar directivas de acceso condicional. Para aprovechar con mayor facilidad Azure AD grupos dinámicos, determine una convención de nomenclatura que identifique de forma única Salas de Teams cuentas de recursos.
-   Si se une Teams Room a Active Directory, prepare una unidad organizativa y un grupo de Active Directory para mantener sus cuentas de equipo y recursos de Salas de Microsoft Teams y, opcionalmente, preparar objetos de directiva de grupo (GPO) para habilitar la comunicación remota de PowerShell.

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>Definir Salas de Microsoft Teams de cuenta de recursos 

En función de los escenarios de colaboración que haya decidido habilitar con la implementación de Salas de Microsoft Teams, deberá determinar las características y capacidades que asigne a cada sala de Microsoft Teams que habilite.

| **Escenario** | **Descripción** | **Salas de Microsoft Teams cuenta de servicio** |
|---------- |------------- | --- |
| Reuniones interactivas            | Usar la voz, el vídeo y el uso compartido de pantalla; convertir el Salas de Microsoft Teams en un recurso que se puede reservar                     | Habilitado para Microsoft Teams o Skype Empresarial; habilitado para Exchange (buzón de recursos) |
| Conferencia de acceso telefónico local            | Tener un número de teléfono de audioconferencia al pulsar "Nueva reunión" en la consola | Habilitado para audioconferencias                                          |
| Llamadas RTC salientes o entrantes | Habilitar la Salas de Microsoft Teams para realizar y recibir llamadas RTC                                         | Habilitado para Sistema telefónico                                                |

Para obtener más información sobre Salas de Microsoft Teams cuentas, vea [Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md).


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![soporte técnico para escenarios.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida qué escenarios admitirá e identifique los requisitos de licencias para sus Salas de Microsoft Teams recursos.</li></ul>| 
| ![preparar el equipo host.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Prepararse para hospedar cuentas de equipo y recursos.</li></ul>| 


_Ejemplo Salas de Microsoft Teams tabla de planificación de cuentas de recursos_

| **Sitio**  | **Nombre del salón** | **Tipo de salón** | **Capacidades de sala futuras**                                                 | **Salas de Microsoft Teams de cuenta**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Sede de Londres | Curie         | Medio        | 1 pantalla, audio y vídeo más presentación <br>Acceso a conferencias de acceso telefónico local<br> Acceso RTC  | Habilitado para Exchange (buzón de recursos) <br>Habilitado para audioconferencias <br>Habilitado para Sistema telefónico |
| Sydney HQ | Hill          | Grande         | 2 pantallas, audio y vídeo más presentación<br>Acceso a conferencias de acceso telefónico local<br> Acceso RTC  | Habilitado para Skype Empresarial <br>Habilitado para Exchange (buzón de recursos)<br> Habilitado para audioconferencias <br>Habilitado para Sistema telefónico |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>Prepararse para hospedar cuentas Salas de Microsoft Teams recursos (opcional)

Para que pueda administrar e informar sobre sus cuentas Salas de Microsoft Teams recursos, prepare su cuenta local de Active Directory o Azure Active Directory (Azure AD). 

Defina un grupo local de Active Directory o Azure Active Directory para agregar todas las Salas de Microsoft Teams de recursos locales. Si usa Azure Active Directory, considere la posibilidad de usar un grupo dinámico para agregar y quitar automáticamente cuentas de recursos del grupo.

Defina una unidad organizativa en la jerarquía local de Active Directory para que tenga todas las cuentas de equipo de Salas de Microsoft Teams (si están unidas al dominio) y una unidad organizativa para mantener todas las cuentas de usuario Salas de Microsoft Teams usuario. Deshabilite la herencia de directivas de grupo para asegurarse de que solo se aplican las directivas que tenía previsto aplicar a las directivas Salas de Microsoft Teams.

Cree un objeto de directiva de grupo asignado a la unidad de organización que contiene Salas de Microsoft Teams cuentas de equipo. Use esta opción para: 

-   [Establecer la configuración de la cuenta local y de energía.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Habilite Windows actualización.
-   Habilitar la comunicación remota de PowerShell. Puede configurar un script de inicio para ejecutar un script: Enable-PSRemoting -Force

Puede usar PowerShell para realizar varias actividades de administración remota, como obtener y configurar información de configuración. La comunicación remota de  PowerShell debe habilitarse antes de que se pueda llevar a cabo cualquier administración remota de PowerShell y debe considerarse como parte de los procesos de implementación o configurarse a través de la directiva de grupo. Para obtener más información sobre estas capacidades y habilitarlas, vea [Mantenimiento y operaciones.](rooms-operations.md#remote-management-using-powershell) 


## <a name="configuration-and-deployment"></a>Configuración e implementación 

La planificación de la configuración y la implementación abarca las siguientes áreas clave:

-   Aprovisionamiento de cuentas de recursos
-   Instalación del software del dispositivo
-   Implementación de dispositivos
-   Salas de Microsoft Teams de aplicaciones y dispositivos periféricos
-    Pruebas
-   Administración de activos

### <a name="resource-account-provisioning"></a>Aprovisionamiento de cuentas de recursos 

Cada Salas de Microsoft Teams dispositivo requiere una cuenta de recursos dedicada y única que debe estar habilitada para Microsoft Teams o Skype Empresarial y Exchange. Esta cuenta debe tener un buzón de sala hospedado en Exchange. El procesamiento del calendario debe configurarse para que el dispositivo pueda aceptar automáticamente las solicitudes de reunión entrantes. Para obtener más información sobre cómo crear estas cuentas, vea [Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md). 

**Pro sugerencia:** cada Salas de Microsoft Teams debe tener un nombre de equipo válido y único en la red. Muchos sistemas de supervisión y alertas muestran el nombre del equipo como un identificador de clave, por lo que es importante desarrollar una convención de nomenclatura para implementaciones de Salas de Microsoft Teams que permita al personal de soporte técnico localizar fácilmente el Salas de Microsoft Teams que se ha marcado como que requiere una acción. Un ejemplo puede ser usar un patrón de MTR-*Nombre del* salón - *de sitio* (MTR-LON-CURIE). 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![decidir convención de nomenclatura.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la convención de nomenclatura para sus Salas de Microsoft Teams de recursos.</li><li>Decida si va a crear cuentas individuales o usar scripts de aprovisionamiento masivo.</li></ul>| 
| ![pasos siguientes.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empiece a planear la implementación del dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalación del software del dispositivo 

Salas de Teams viene preinstalado por el fabricante de equipos original (OEM).

Proporcionamos instrucciones sobre cómo usar [Microsoft Azure Monitor](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) para supervisar la implementación de Salas de Microsoft Teams e informar sobre la disponibilidad, errores de hardware/software y Salas de Microsoft Teams versión de la aplicación. Si decide usar Microsoft Operations Management Suite, debe instalar el agente de Operations Management Suite como parte del proceso de instalación del software y configurar la información de conexión del área de trabajo para el área de trabajo. 

Una consideración adicional es si el Salas de Microsoft Teams se unirá al dominio. Encontrará información sobre las ventajas de la unión a dominios en [Configurar la directiva](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)de grupo para Salas de Microsoft Teams . 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![nombres de dispositivos de puntos de decisión.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la convención Salas de Microsoft Teams nombre de cuenta de recursos que se usará durante la implementación.</li><li>Decida si se unirá a Salas de Microsoft Teams dispositivos a su dominio. </li><li>Decida si usará Azure Monitor para supervisar la Salas de Microsoft Teams implementación.</li> 
| ![dispositivo del plan de pasos siguientes.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Empiece a planear el enfoque de implementación de dispositivos.</li></ul>| 


### <a name="device-deployment"></a>Implementación de dispositivos

Después de decidir cómo crear y administrador las cuentas de recursos de Salas de Microsoft Teams, cree su plan para enviar los dispositivos y sus periféricos asignados a sus salas y, después, continúe con la instalación y configuración.


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![administrar la implementación de sitio por sitio.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida quién administrará la implementación de sitio por sitio.</li><li> Identifique los recursos que instalarán Salas de Microsoft Teams en el sitio y realice la configuración y las pruebas.</li></ul>| 
| ![iniciar pruebas de dispositivos.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Iniciar pruebas de dispositivos.</li></ul>| 

_Tabla de implementación de ejemplo_

| **Sitio**  | **Nombre del salón** | **Tipo de salón** | **Salas de Microsoft Teams sistema**  | **Dispositivos periféricos**  | **Salas de Microsoft Teams nombre del equipo**  | **Salas de Microsoft Teams de recursos**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| Sede de Londres | Curie         | Medio        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Salas de Microsoft Teams de aplicaciones y dispositivos periféricos 

Después de que cada Salas de Microsoft Teams sistema se haya implementado físicamente y se hayan conectado los dispositivos periféricos compatibles, deberá configurar la aplicación Salas de Microsoft Teams para asignar la cuenta de recurso y la contraseña Salas de Microsoft Teams habilitar Salas de Teams iniciar sesión en Microsoft Teams o Skype Empresarial y Exchange.

Puede configurar manualmente cada Salas de Microsoft Teams sistema. Como alternativa, puede usar un archivo de configuración XML almacenado de forma centralizada por Salas de Teams para administrar la configuración de la aplicación.

Para obtener más información sobre cómo usar el archivo de configuración XML, vea Administrar una configuración de Salas de Microsoft Teams consola de forma remota [con un archivo de configuración XML.](xml-config-file.md) 

Puede usar [PowerShell remoto](rooms-operations.md#remote-management-using-powershell) para extraer la Salas de Microsoft Teams configuración de informes. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![configurar el punto de decisión.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si va a configurar manualmente cada sistema Salas de Microsoft Teams o usar un archivo XML central (uno por Salas de Microsoft Teams dispositivo).</li></ul>| 
| ![siguiente enfoque remoto de pasos.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Definir el enfoque de administración remota.</li></ul>| 

### <a name="testing"></a> Pruebas

Después Salas de Teams se ha implementado, debe probarlo. Compruebe que las funcionalidades [enumeradas en Salas de Microsoft Teams ayuda](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us) están trabajando en el dispositivo implementado. Recomendamos encarecidamente que el equipo de implementación compruebe que Salas de Microsoft Teams está apareciendo en Teams centro de administración. También es importante que realice una serie de llamadas de prueba y reuniones para comprobar la calidad. Para obtener más información, vea esta lista [de comprobación de implementación útil.](console.md#microsoft-teams-rooms-deployment-checklist)

Le recomendamos que, como parte de la implementación general de Teams o Skype Empresarial, configure la creación de archivos para el Panel de calidad de llamadas (CQD), supervise las tendencias de calidad y participe en el proceso de revisión de calidad de la experiencia. Para obtener más información, vea [Mejorar y supervisar la calidad de](../monitor-call-quality-qos.md)las llamadas para Teams . 

### <a name="asset-management"></a>Administración de activos

Como parte de la implementación, querrá actualizar el registro de activos con el nombre del salón, Salas de Microsoft Teams nombre, Salas de Microsoft Teams cuenta de recursos y dispositivos periféricos asignados. 

_Tabla de activos de ejemplo_

| **Sitio**  | **Nombre del salón** | **Tipo de salón** | **Salas de Microsoft Teams serie no.**  | **Dispositivos periféricos/ números de serie./ Puertos**  | **Salas de Microsoft Teams nombre del equipo**  | **Salas de Microsoft Teams de servicio**  | **Fecha implementada** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| Sede de Londres | Curie         | Medio        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |
