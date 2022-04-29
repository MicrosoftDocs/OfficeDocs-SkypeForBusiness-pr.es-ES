---
title: Implementar Salas de Microsoft Teams
ms.author: czawideh
author: cazawideh
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
ms.openlocfilehash: 18a5d72fb9c11b34bb994734b8d064c3aaa2cdae
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125775"
---
# <a name="deployment-overview"></a>Introducción general a la implementación

La implementación de Salas de Microsoft Teams básicamente se divide en fases:

- Confirmación de que las ubicaciones de implementación (espacios) cumplen las dependencias de implementación
- Crear Microsoft Teams o Skype Empresarial y Exchange cuentas y asignarlas a Salas de Teams (consulte [Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md))
- (Opcional) Configurar Azure Monitor para los sistemas (consulte [Implementar la administración de Salas de Microsoft Teams con Azure Monitor](azure-monitor-deploy.md)
- Configurar Salas de Teams en espacios de reuniones y conectar los dispositivos periféricos que necesitas (consulta la documentación del OEM de tu conjunto de dispositivos)

## <a name="site-readiness"></a>Disponibilidad del sitio 

Mientras se entregan los dispositivos ordenados a su organización, trabaje con sus equipos de redes, instalaciones y AV para asegurarse de que se cumplen las dependencias de implementación y de que cada sitio y espacio está listo en términos de potencia, redes y pantalla. Además, asegúrate de que se cumplan los requisitos de instalación física. Para consideraciones de instalación física, consulte con su proveedor y aproveche la experiencia de su equipo de AV al instalar y montar pantallas y el cableado.

Puede obtener más información sobre estas dependencias en los siguientes vínculos de instrucciones de planeación:

-   [Comprobar la disponibilidad de red](rooms-prep.md#check-network-availability)
-   [Certificados](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**sugerencia de Pro**: si necesita usar servidores proxy para proporcionar acceso a Teams, [revise primero este artículo](../proxy-servers-for-skype-for-business-online.md). Cuando se trata de Microsoft Teams tráfico multimedia en tiempo real a través de servidores proxy, recomendamos omitir los servidores proxy por completo. Microsoft Teams tráfico ya está cifrado, por lo que los servidores proxy no lo hacen más seguro y agregan latencia al tráfico en tiempo real. Como parte de la implementación más amplia, le recomendamos que siga las instrucciones de [Preparar la red para Teams](../prepare-network.md) para planear el ancho de banda y evaluar la idoneidad de la red para el tráfico en tiempo real.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![confirmar sitios.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Confirme que los sitios cumplen los requisitos clave para Salas de Microsoft Teams.</li><li>Confirme que ha proporcionado ancho de banda suficiente para cada sitio.</li></ul>| 
| ![planear la implementación de dispositivos.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Comienza a planear la implementación y configuración de tu dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Preparación del servicio

Para preparar la implementación de Salas de Microsoft Teams, realice las siguientes tareas centrales clave:

-   Definir Salas de Microsoft Teams cuentas de recursos.
-   Si se une a Salas de Teams a Azure Active Directory, prepare un grupo de Azure AD con pertenencia dinámica para que contenga todas las cuentas de recursos Salas de Teams. Esto simplificará la administración futura, como aplicar directivas de acceso condicional. Para aprovechar más fácilmente Azure AD grupos dinámicos, determine una convención de nomenclatura que identifique de forma exclusiva Salas de Teams cuentas de recursos.
-   Si se une Salas de Teams a Active Directory, prepare una unidad organizativa y un grupo de Active Directory para que mantenga su Salas de Microsoft Teams cuenta de recursos y del equipo y, opcionalmente, prepare directiva de grupo objetos (GPO) para habilitar PowerShell remoto.

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>Definir Salas de Microsoft Teams características de cuenta de recursos 

Según los escenarios de colaboración que haya decidido habilitar con la implementación de Salas de Microsoft Teams, tendrá que determinar las características y capacidades que asigne a cada Salas de Microsoft Teams que habilite.

| **Escenario** | **Descripción** | **característica de cuenta de servicio de Salas de Microsoft Teams** |
|---------- |------------- | --- |
| Reuniones interactivas            | Uso de voz, vídeo y uso compartido de pantalla; convertir la Salas de Microsoft Teams en un recurso reservable                     | Habilitado para Microsoft Teams o Skype Empresarial; habilitado para Exchange (buzón de recursos) |
| Conferencia de acceso telefónico local            | Tener un número de teléfono de audioconferencia al pulsar "Nueva reunión" en la consola | Habilitado para audioconferencia                                          |
| Llamadas RTC de entrada o salida | Habilitar la consola de Salas de Microsoft Teams para realizar y recibir llamadas RTC                                         | Habilitado para Sistema telefónico                                                |

Para obtener más información sobre las cuentas de Salas de Microsoft Teams, vea [Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md).


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![compatibilidad con escenarios.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida qué escenarios admitirá e identifique los requisitos de licencia para sus cuentas de recursos de Salas de Microsoft Teams.</li></ul>| 
| ![preparar equipo host.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Prepararse para hospedar cuentas de equipos y recursos.</li></ul>| 


_Ejemplo Salas de Microsoft Teams tabla de planificación de cuentas de recursos_

| **Sitio**  | **Nombre de la sala** | **Tipo de sala** | **Capacidades futuras de la sala**                                                 | **características de la cuenta de Salas de Microsoft Teams**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| SEDE de Londres | Curie         | Medio        | 1 pantalla, audio y vídeo y presentación <br>Acceso a conferencias de acceso telefónico local<br> Acceso RTC  | Habilitado para Exchange (buzón de recursos) <br>Habilitado para audioconferencia <br>Habilitado para Sistema telefónico |
| Sede de Sydney | Colina          | Grande         | 2 pantallas, audio y vídeo más presentación<br>Acceso a conferencias de acceso telefónico local<br> Acceso RTC  | Habilitado para Skype Empresarial <br>Habilitado para Exchange (buzón de recursos)<br> Habilitado para audioconferencia <br>Habilitado para Sistema telefónico |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>Prepararse para hospedar cuentas de Salas de Microsoft Teams y recursos (opcional)

Para que pueda administrar las cuentas de Salas de Microsoft Teams y recursos e informar de estas, prepare su Active Directory local o Azure Active Directory (Azure AD). 

Defina una Active Directory local o un grupo de Azure Active Directory al que agregar todas las cuentas de recursos de Salas de Microsoft Teams. Si usa Azure Active Directory, considere la posibilidad de usar un grupo dinámico para agregar y quitar automáticamente cuentas de recursos del grupo.

Defina una unidad organizativa en la jerarquía de Active Directory local para mantener todas las cuentas de equipo Salas de Microsoft Teams (si están unidas al dominio) y una unidad organizativa para almacenar todas las cuentas de usuario de Salas de Microsoft Teams. Deshabilite directiva de grupo herencia para asegurarse de que solo se aplican las directivas que quería aplicar a la Salas de Microsoft Teams unido a un dominio.

Cree un objeto de directiva de grupo asignado a la unidad de organización que contenga sus cuentas de Salas de Microsoft Teams equipo. Use esta opción para: 

-   [Establecer la configuración de la cuenta local y de energía](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Habilitar Windows Update.
-   Habilitar La comunicación remota de PowerShell. Puede configurar un script de inicio para ejecutar un script: Enable-PSRemoting -Force

Puede usar PowerShell para realizar varias actividades de administración remota, incluida la obtención y configuración de información de configuración. PowerShell remoto debe estar habilitado *antes* de que cualquier administración remota de PowerShell pueda tener lugar y debe considerarse como parte de sus procesos de implementación o configurado a través de directiva de grupo. Para obtener más información sobre estas capacidades y habilitarlas, consulte [Mantenimiento y operaciones](rooms-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuración e implementación 

La planificación de la configuración y la implementación abarca las siguientes áreas clave:

-   Aprovisionamiento de cuentas de recursos
-   Instalación de software de dispositivo
-   Implementación de dispositivos
-   configuración de dispositivos periféricos y aplicaciones Salas de Microsoft Teams
-    Pruebas
-   Administración de activos

### <a name="resource-account-provisioning"></a>Aprovisionamiento de cuentas de recursos 

Cada dispositivo de Salas de Microsoft Teams requiere una cuenta de recursos dedicada y única que se debe habilitar para Microsoft Teams o Skype Empresarial y Exchange. Esta cuenta debe tener un buzón de sala hospedado en Exchange. El procesamiento del calendario debe configurarse para que el dispositivo pueda aceptar automáticamente las convocatorias de reunión entrantes. Para obtener más información sobre cómo crear estas cuentas, vea [Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md). 

**sugerencia de Pro**: cada Salas de Microsoft Teams debe tener un nombre de equipo único y válido en la red. Muchos sistemas de supervisión y alerta muestran el nombre del equipo como un identificador de clave, por lo que es importante desarrollar una convención de nomenclatura para implementaciones de Salas de Microsoft Teams que permita al personal de soporte localizar fácilmente el Salas de Microsoft Teams que se ha marcado como que requiere una acción. Un ejemplo podría estar usando un patrón de NOMBRE *MTR-SiteRoom*- (MTR-LON-CURIE). 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![decida la convención de nomenclatura.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la convención de nomenclatura para las cuentas de recursos de Salas de Microsoft Teams.</li><li>Decida si va a crear cuentas individuales o usar scripts de aprovisionamiento masivo.</li></ul>| 
| ![pasos siguientes.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Comienza a planear la implementación de tu dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalación de software de dispositivo 

Salas de Teams viene preinstalado por el fabricante de equipos originales (OEM).

Proporcionamos instrucciones sobre cómo usar [Microsoft Azure Monitor](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) para supervisar la implementación de Salas de Microsoft Teams e informar sobre disponibilidad, errores de hardware o software y Salas de Microsoft Teams versión de la aplicación. Si decide usar Microsoft Operations Management Suite, debe instalar el agente de Operations Management Suite como parte del proceso de instalación de software y configurar la información de conexión del área de trabajo para su área de trabajo. 

Una consideración adicional es si el Salas de Microsoft Teams se unirá a un dominio. Encontrará información sobre las ventajas de la unión a un dominio en [Configuración de directiva de grupo para Salas de Microsoft Teams](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms). 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![nombres de dispositivos de puntos de decisión.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida la convención de nomenclatura Salas de Microsoft Teams cuenta de recursos que se usará durante la implementación.</li><li>Decida si va a unir Salas de Microsoft Teams dispositivos a su dominio. </li><li>Decida si usará Azure Monitor para supervisar la implementación de Salas de Microsoft Teams.</li> 
| ![siguiente dispositivo de planeación de pasos.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Comienza a planear el enfoque de implementación de dispositivos.</li></ul>| 


### <a name="device-deployment"></a>Implementación de dispositivos

Después de decidir cómo crear y administrar las cuentas de recursos de Salas de Microsoft Teams, cree su plan para enviar los dispositivos y los periféricos asignados a sus salas y, a continuación, continúe con la instalación y configuración.


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![administrar la implementación de sitio a sitio.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida quién administrará la implementación de sitio por sitio.</li><li> Identifique los recursos que instalarán Salas de Microsoft Teams en el sitio y realice la configuración y las pruebas.</li></ul>| 
| ![iniciar pruebas de dispositivos.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Iniciar pruebas de dispositivos.</li></ul>| 

_Tabla de implementación de ejemplo_

| **Sitio**  | **Nombre de la sala** | **Tipo de sala** | **sistema Salas de Microsoft Teams**  | **Dispositivos periféricos**  | **Salas de Microsoft Teams nombre del equipo**  | **Salas de Microsoft Teams cuenta de recursos**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| SEDE de Londres | Curie         | Medio        |                                   |                  |                                          |                                             |
| Sede de Sydney | Colina          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>configuración de dispositivos periféricos y aplicaciones Salas de Microsoft Teams 

Después de implementar físicamente cada Salas de Microsoft Teams sistema y conectar los dispositivos periféricos compatibles, tendrás que configurar la aplicación Salas de Microsoft Teams para asignar la cuenta de recurso de Salas de Microsoft Teams y la contraseña para habilitar Salas de Teams iniciar sesión en Microsoft Teams o Skype Empresarial y Exchange.

Puede configurar manualmente cada sistema Salas de Microsoft Teams. Como alternativa, puede usar un archivo de configuración XML almacenado de forma centralizada Salas de Teams para administrar la configuración de la aplicación.

Para obtener más información sobre cómo usar el archivo de configuración XML, vea [Administrar una configuración de consola de Salas de Microsoft Teams de forma remota con un archivo de configuración XML](xml-config-file.md). 

Puede usar [PowerShell remoto](rooms-operations.md#remote-management-using-powershell) para extraer la configuración de Salas de Microsoft Teams para las necesidades de creación de informes. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![configuración del punto de decisión.](../media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Decida si configura manualmente cada sistema Salas de Microsoft Teams o si usa un archivo XML central (uno por Salas de Microsoft Teams dispositivo).</li></ul>| 
| ![pasos siguientes: enfoque remoto.](../media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Defina su enfoque de administración remota.</li></ul>| 

### <a name="testing"></a> Pruebas

Después de implementar Salas de Teams, debe probarlo. Comprueba que las funciones enumeradas en [Salas de Microsoft Teams ayuda](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us) funcionan en el dispositivo implementado. Recomendamos encarecidamente que el equipo de implementación compruebe que Salas de Microsoft Teams aparece en Teams centro de administración. También es importante que realice una serie de llamadas de prueba y reuniones para comprobar la calidad. Para obtener más información, consulte esta [útil lista de comprobación de implementación](console.md#microsoft-teams-rooms-deployment-checklist).

Le recomendamos que, como parte de la Teams general o la implementación de Skype Empresarial, configure archivos de creación para el Panel de calidad de llamadas (CQD), supervise las tendencias de calidad y participe en el proceso de revisión de la calidad de la experiencia. Para obtener más información, consulte [Mejorar y supervisar la calidad de las llamadas para Teams](../monitor-call-quality-qos.md). 

### <a name="asset-management"></a>Administración de activos

Como parte de la implementación, querrá actualizar el registro de activos con el nombre del salón, Salas de Microsoft Teams nombre, Salas de Microsoft Teams cuenta de recursos y dispositivos periféricos asignados. 

_Tabla de activos de ejemplo_

| **Sitio**  | **Nombre de la sala** | **Tipo de sala** | **Salas de Microsoft Teams n.º de serie.**  | **Dispositivos periféricos/ nos seriales./ Puertos**  | **Salas de Microsoft Teams nombre del equipo**  | **Salas de Microsoft Teams cuenta de servicio**  | **Fecha de implementación** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| SEDE de Londres | Curie         | Medio        |                                          |                                          |                                          |                                            |                   |
| Sede de Sydney | Colina          | Grande         |                                          |                                          |                                          |                                            |                   |
