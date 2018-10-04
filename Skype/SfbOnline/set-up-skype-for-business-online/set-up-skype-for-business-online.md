---
title: Configurar Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.custom:
- Setup
- Alchemy
- LIL_Placement
description: 'Aprenda a configurar su dominio, los usuarios, mensajería instantánea y presencia para su organización para instalar Skype para la empresa. También vea cómo configurar conferencias de audio, sistema telefónico y llamar a los planes y difusión de reunión de Skype. '
ms.openlocfilehash: af472553cea8a79f2fe9d918f7924f8884e834b5
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374479"
---
# <a name="set-up-skype-for-business-online"></a>Configurar Skype Empresarial Online

Debe contar con permisos de administrador global de Office 365 para poder configurar Skype Empresarial. Si tiene un servidor proxy o firewall que restringe el acceso a algunas partes de la web, analice la posibilidad de contratar a un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que configure Skype Empresarial en su lugar.

## <a name="setting-up-skype"></a>Configurar Skype

Parece que necesita ayuda para configurar Skype con su suscripción de Office 365. Siga los pasos que se detallan en este artículo para completar la configuración.

## <a name="1-plan-for-skype-for-business"></a>1. Plan para Skype Empresarial

Si tiene **[Office 365 Empresa Premium](https://products.office.com/en-us/business/office-365-business-premium)** o **Empresa Essentials**, puede usar Skype Empresarial para realizar llamadas en línea a otros contactos de su empresa que se encuentran en su suscripción. Por ejemplo, si su empresa tiene 10 personas, podrá [empezar a usar Skype para la empresa para la mensajería instantánea y reuniones en línea](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) y [las reuniones con Skype para la empresa](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) mediante Skype para la empresa después de realizar los pasos 2 a 6 que aparece a continuación. Y se puede [configurar un Skype para la reunión de negocios en Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) para reuniones en línea, demasiado!

Si quiere usar Skype Empresarial para hacer y recibir **llamadas** de personas *externas*  a su empresa:

- **Opción 1. Usar la [aplicación Skype](https://www.skype.com/)**. Si tiene una empresa muy pequeña (por ejemplo, 1 o 2 personas), la aplicación de Skype es la mejor solución. Es más económica para las llamadas nacionales e internacionales. Aún puede las llamadas de conferencia, realizar llamadas de vídeo y compartir el escritorio para las presentaciones. [Compruebe las tarifas y las opciones de pago](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).

- **Opción 2. Actualizar su plan y comprar el sistema telefónico y un plan de llamadas de Office 365**. La forma más sencilla para averiguar cuánto esto cuesta y, a continuación, cambiar, es a [soporte de contacto para los productos de negocio - ayuda de administración](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) y que ellos todo para usted.

Para obtener más información, vea [Planear el programa de instalación de Office 365 para la empresa](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).

## <a name="2-sign-in-to-office-365"></a>2. Iniciar sesión en Office 365
<a name="bkmk_signin"> </a>

Skype Empresarial Online forma parte del conjunto de servicios de Office 365. Para configurar Skype Empresarial Online debe iniciar sesión en Office 365. A continuación se explica cómo debe hacerlo:

1. Busque su Id. de usuario de Office 365 (por ejemplo,  <em>rob@fourthcoffee.com</em>  ). Lo podrá encontrar en un correo electrónico que le envió el equipo de Microsoft Online Services con el Id. de usuario de Office 365 que creó cuando compró Skype Empresarial Online. El correo tiene un aspecto similar a este:

    ![Un ejemplo del correo electrónico de bienvenida que recibió al suscribirse a Skype Empresarial Online. Contiene su Id. de usuario de Office 365.](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. Inicie sesión en el centro de administración de Office 365 y escriba su identificador de usuario de Office 365 y la contraseña. Después de iniciar sesión, verá el centro de administración de Office 365:

    ![Un ejemplo del aspecto del centro de administración de Office 365 cuando se tiene un plan online de Skype Empresarial.](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)

## <a name="3-set-up-your-domain-and-users"></a>3. Configurar el dominio y los usuarios
<a name="bkmk_users"> </a>

Ahora que ha iniciado sesión en Office 365, puede configurar el dominio y las personas de su organización para utilizar Skype Empresarial Online.

1. [Agregar un dominio y los usuarios a Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): usar el Asistente para la instalación de Office 365 para configurar su dominio personalizado (por ejemplo, *fourthcoffee.com*) con Office 365. **De forma predeterminada, el asistente de instalación de Office 365 incluye la configuración de Skype Empresarial Online y la creación de sus id. de usuario de Skype Empresarial.** Si ya ha usado el asistente para instalar el dominio para Office 365, ya habría completado este paso.

2. [Comprobar el dominio y las conexiones DNS](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): Use nuestra herramienta, el solucionador de problemas de dominios, para comprobar si la configuración DNS y la configuración del dominio son correctas. Si usa esta herramienta ahora, contribuirá en gran medida a determinar los problemas de configuración posteriormente, ya que podrá eliminar la configuración DNS como el origen de problemas futuros.

3. [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): la mayoría de las empresas pequeñas no necesitan realizar este paso. **Pero si tiene un servidor proxy o un firewall que restringe el acceso a elementos de la web**, deberá crear reglas para permitir el acceso a los puntos de conexión de Skype Empresarial Online. Este es un paso complejo que sería mejor que realizara un experto en la configuración de firewalls y servidores proxy. Si no ha hecho esto antes, considere la posibilidad de contratar a un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para configurar Skype para la empresa para usted.

## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. Configurar la mensajería instantánea y la presencia en su organización
<a name="bkmk_IM"> </a>

La mensajería instantánea (MI) y la presencia ([Controlar el acceso a la información de presencia en Skype Empresarial](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) son características básicas que se incluyen con Skype Empresarial. De forma predeterminada, los miembros de su empresa pueden usar Skype y la mensajería instantánea para comunicarse entre ellos.

1. **Elegir con quién más quiere que se puedan comunicar los usuarios de Skype Empresarial:**

   - [Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial](allow-users-to-contact-external-skype-for-business-users.md) Es necesario configurar los sistemas en su empresa *y*  en la empresa externa.

     **IMPORTANTE**: Si tiene dos dominios en su empresa, como rob@contosowest.com e ina@contosoeast.com, debe seguir este paso para que todos los usuarios puedan comunicarse entre ellos.

   - [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) externos a la empresa

2. **Elegir quién podrá ver si los compañeros de trabajo están conectados:** la característica de presencia muestra quién está conectado y cuál es su disponibilidad (por ejemplo, disponible, ocupado, ausente o presentando).

    ![An example of a person's online status with a personal message.](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    Puede elegir la configuración predeterminada para todos los usuarios de su empresa:

   - Mostrar automáticamente la presencia en línea de un usuario a todos los usuarios de la organización

   - Mostrar la presencia en línea de un usuario solo a sus contactos

Para obtener instrucciones, consulte [Configurar la presencia en Skype Empresarial Online](configure-presence-in-skype-for-business-online.md).

## <a name="5-download-and-install-skype-for-business"></a>5. Descargar e instalar Skype Empresarial
<a name="bkmk_download"> </a>

Para usar Skype Empresarial en su equipo PC, su equipo Mac o en un dispositivo móvil, todos los usuarios de su empresa deben instalar primero la descarga de Skype Empresarial en sus dispositivos.

- [Instalar Skype Empresarial](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): instrucciones sobre cómo descargar la aplicación del portal de Office 365 e instalarlo en su PC o Mac.

- [Implementar el Skype para cliente empresarial en Office 365](deploy-the-skype-for-business-client-in-office-365.md): instrucciones para la implementación de la aplicación en una empresa grande.

- [Instalar Skype Empresarial](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): descargue, instale e inicie sesión en Skype Empresarial en dispositivos Android, dispositivos iOS y teléfonos Windows.

- [Activar o desactivar las notificaciones de teléfono móvil](turn-on-or-off-mobile-phone-notifications.md): cuando tenga Skype para la empresa instalado en un dispositivo móvil, usted y otros usuarios en su negocio pueden recibir alertas acerca de los mensajes instantáneos entrantes y perdidas.

## <a name="6-test-to-make-sure-everything-is-working"></a>6. Realizar pruebas para asegurarse de que todo funciona
<a name="bkmk_test"> </a>

En primer lugar, compruebe si tanto su usuario como el resto de los usuarios de su empresa pueden [Vídeo: Iniciar y cerrar sesión en Skype Empresarial](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451). Compruebe si pueden enviarse mensajes instantáneos y ver la presencia del resto de usuarios. Prueben también a realizar una reunión rápida.

¿Tiene algún problema? Siga este procedimiento:

- [¿Necesita ayuda para iniciar sesión en Skype Empresarial?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) con los problemas de inicio de sesión comunes.

- [Póngase en contacto con el soporte de Office 365 para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). Estamos aquí para ayudarle.

## <a name="do-you-want-to-set-up-other-available-features"></a>¿Desea configurar otras características disponibles?
<a name="bkmk_more"> </a>

Antes de configurar más características, asegúrese de tener licencias para poder usarlas. [Licencias complementarias de Skype Empresarial y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a>Configurar Audioconferencia

En algunas ocasiones, en su organización se necesitará un teléfono para llamar a una reunión. Skype Empresarial incluye la característica de Audioconferencia para este tipo de situaciones. Las personas pueden llamar a las reuniones de Skype Empresarial con un teléfono en lugar de hacerlo con la aplicación de Skype Empresarial en un dispositivo móvil o PC.

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>Configurar Sistema telefónico y Plan de llamadas de Office 365

La característica de Sistema telefónico de Office 365 le brinda un sistema telefónico para la empresa. Las llamadas a otros usuarios de Skype Empresarial de su empresa son gratuitas y los empleados pueden recibir correos de voz de otros empleados u otros usuarios externos. Esto es lo que obtiene con Sistema telefónico.

Al agregar el servicio Plan de llamadas, los empleados reciben un número de teléfono principal en Skype Empresarial. Pueden realizar llamadas telefónicas a números externos a la empresa o recibirlas de ellos. Pueden realizar llamadas de voz entre teléfonos VoIP, equipos y dispositivos móviles. En caso de emergencia, pueden llamar al 911 para obtener ayuda.

Si desea ver instrucciones detalladas para la configuración, vea Configurar Planes de llamadas.

### <a name="set-up-skype-meeting-broadcast"></a>Configurar Difusión de reunión de Skype

Difusión de reunión de Skype es una característica que le permite producir, hospedar y difundir reuniones con hasta 10 000 asistentes. **Para obtener más información sobre cómo funciona, vea [¿Qué es una Difusión de reunión de Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**.

A continuación se muestra una introducción a los pasos para configurar Difusión de reunión de Skype:

1. [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): asigne licencias de **Skype Empresarial Online** o **Enterprise Plan** a todo aquel que vaya a **hospedar** una reunión de difusión.

2. [Habilitar la difusión de reunión de Skype](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): de forma predeterminada, esta característica no está habilitada. Después de activarla, los usuarios podrán hospedar reuniones de difusión con otros miembros de su organización.

3. [Configurar la red para difundir presentación de reunión de Skype](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): si desea seminarios Web de host y otras difusiones con los asistentes externos a su organización, debe configurar la red.

4. [Programación de una difusión de reunión de Skype](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) y tiene una [unirse a una difusión de reunión de Skype](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): realizar reuniones difusión seguro que funcionan mediante la programación de una difusión de reunión de Skype en *https://portal.broadcast.skype.com* y, a continuación, tener una persona intenta unirse a la reunión.

## <a name="learn-about-network-connectivity-requirements"></a>Aprender acerca de los requisitos de conectividad de red
<a name="bkmk_more"> </a>

La calidad de audio, vídeo y uso compartido de la aplicación en Skype Empresarial se ve enormemente afectada por la calidad de la conectividad de red de punto a punto Para una experiencia óptima, es importante asegurarse de que exista una conexión de buena calidad entre la red de la empresa y Skype Empresarial Online. Para obtener información sobre red y optimización, vea [Optimización del rendimiento de Skype Empresarial Online](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>¿Ha terminado la configuración? Introducción a Skype Empresarial
<a name="bkmk_more"> </a>

[Skype para realizar un curso de negocio](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): desproteger esta lista de temas de aprendizaje para ayudar a empezar rápidamente!

[Iniciar una llamada de conferencia de Skype Empresarial](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[Configurar las opciones de los dispositivos de vídeo en Skype Empresarial](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[Realizar y recibir una videollamada con Skype Empresarial](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Temas relacionados
<a name="bkmk_more"> </a>

[Planificar la conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online](https://go.microsoft.com/fwlink/p/?linkid=400791)



