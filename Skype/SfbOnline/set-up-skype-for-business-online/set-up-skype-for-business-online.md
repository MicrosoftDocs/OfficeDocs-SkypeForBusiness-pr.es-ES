---
title: Configurar Skype Empresarial Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- Alchemy
- LIL_Placement
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
description: 'Aprende a configurar tu dominio, usuarios, mensajería instantánea y presencia para que tu organización instale Skype empresarial. Consulta también cómo configurar la conferencia de audio, el sistema telefónico y los planes de llamadas, y la transmisión de reuniones de Skype. '
ms.openlocfilehash: fcca1a3181ca0f5753fd53811290d710e8030064
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239812"
---
# <a name="set-up-skype-for-business-online"></a>Configurar Skype Empresarial Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Debe tener permisos de administrador global para configurar Skype Empresarial. Si tiene un servidor proxy o firewall que restringe el acceso a algunas partes de la web, analice la posibilidad de contratar a un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que configure Skype Empresarial en su lugar.

## <a name="setting-up-skype"></a>Configurar Skype

Parece que necesita ayuda para configurar Skype con su Microsoft 365 o Office 365 suscripción. Puede seguir los pasos de este artículo para finalizar la configuración.

## <a name="1-plan-for-skype-for-business"></a>1. Planificar Skype Empresarial Server

Si tiene Microsoft 365 Empresa Premium **[Estándar](https://products.office.com/business/office-365-business-premium)** o **Business Essentials,** puede usar Skype Empresarial realizar llamadas en línea a otras personas de su empresa que estén en su suscripción. Por ejemplo, si su empresa tiene 10 personas, podrá[Empezar a usar Skype Empresarial para mensajería instantánea y reuniones en línea](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) entre todas, así como[Meetings with Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) mediante Skype Empresarial tras realizar los pasos del 2 al 6 que se encuentran a continuación. ¡También podrá[Configurar una reunión de Skype Empresarial en Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) a esas conferencias en línea!

Si quiere usar Skype Empresarial para hacer y recibir **llamadas** de personas *externas*  a su empresa:

- **Opción 1. Usar la [aplicación Skype](https://www.skype.com/)**. Si tiene una empresa muy pequeña (por ejemplo, 1 o 2 personas), la aplicación de Skype es la mejor solución. Es más económica de usar para llamadas nacionales e internacionales. Aún puede retener llamadas de conferencia, realizar llamadas de vídeo y compartir el escritorio para presentaciones. [Compruebe las tarifas y las opciones de pago](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).

- **Opción 2. Actualizar su plan y comprar el sistema telefónico y un plan de llamadas para Office 365**. La forma más sencilla de averiguar cuánto cuesta y después hacer el cambio es[Póngase en contacto con el servicio de asistencia técnica para productos empresariales: Ayuda de administrador ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) y pedirles que ellos se ocupen de todo.

Para obtener más información, consulte [Planear la configuración de Office 365 para empresas](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).

## <a name="2-sign-in-to-office-365"></a>2. Inicie sesión en Office 365
<a name="bkmk_signin"> </a>

Skype Empresarial Online forma parte del conjunto de servicios de Office 365. Para configurar Skype Empresarial Online debe iniciar sesión en Office 365. A continuación se explica cómo debe hacerlo:

1. Busque su Microsoft 365 o Office 365 de usuario (por ejemplo, <em>rob@fourthcoffee.com</em> ). Recibió un correo electrónico del equipo de Microsoft Online Services que contiene Microsoft 365 o Office 365 de usuario que creó al comprar Skype Empresarial Online. El correo tiene un aspecto similar a este:

    ![Un ejemplo del correo electrónico de bienvenida que recibió después de que se suscribió a Skype Empresarial Online. Contiene su Microsoft 365 o Office 365 de usuario.](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. Inicie sesión en el [centro de administración](https://admin.microsoft.com) y escriba su Microsoft 365 o Office 365 de usuario y contraseña. 

## <a name="3-set-up-your-domain-and-users"></a>3. Configurar el dominio y los usuarios
<a name="bkmk_users"> </a>

Ahora que ha iniciado sesión en Office 365, puede configurar el dominio y las personas de su organización para utilizar Skype Empresarial Online.

1. [Agregar usuarios y un dominio a Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): use el asistente para instalación de Office 365 para configurar su dominio personalizado (por ejemplo, *fourthcoffee.com*) con Office 365. **De forma predeterminada, el asistente de instalación de Office 365 incluye la configuración de Skype Empresarial Online y la creación de sus id. de usuario de Skype Empresarial.** Si ya ha usado el asistente para instalar el dominio para Office 365, ya habría completado este paso.

2. [Comprobar el dominio y las conexiones DNS](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): Use nuestra herramienta, el solucionador de problemas de dominios, para comprobar si la configuración DNS y la configuración del dominio son correctas. Si usa esta herramienta ahora, contribuirá en gran medida a determinar los problemas de configuración posteriormente, ya que podrá eliminar la configuración DNS como el origen de problemas futuros.

3. [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): la mayoría de las empresas pequeñas no necesitan realizar este paso. **Pero si tiene un servidor proxy o un firewall que restringe el acceso a elementos de la web**, deberá crear reglas para permitir el acceso a los puntos de conexión de Skype Empresarial Online. Este es un paso complejo que sería mejor que realizara un experto en la configuración de firewalls y servidores proxy. Si no lo has hecho antes, considera la posibilidad de contratar a un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)para que te configure Skype Empresarial.

## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. configurar mensajería instantánea y presencia en la organización
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

- [Instalar Skype Empresarial:](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)Instrucciones para descargar la aplicación desde el centro de administración de Microsoft 365 e instalarla en su PC o Mac.

- [Implementar el cliente de Skype Empresarial en Office 365](deploy-the-skype-for-business-client-in-office-365.md): instrucciones para implementar la aplicación en una empresa grande.

- [Instalar Skype empresarial](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): descargar, instalar e iniciar sesión en Skype Empresarial en dispositivos Android, en dispositivos iOS y en teléfonos Windows.

- [Activar o desactivar las notificaciones del teléfono móvil](turn-on-or-off-mobile-phone-notifications.md) : si tiene Skype Empresarial instalado en un dispositivo móvil, tanto su usuario como el resto de los usuarios de la empresa pueden recibir alertas sobre los mensajes instantáneos entrantes y perdidos.

## <a name="6-test-to-make-sure-everything-is-working"></a>6. probar para asegurarse de que todo funciona
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

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>Configurar el sistema telefónico y los planes de llamadas en Office 365

La característica de Sistema telefónico de Office 365 le brinda un sistema telefónico para la empresa. Las llamadas a otros usuarios de Skype Empresarial de su empresa son gratuitas y los empleados pueden recibir correos de voz de otros empleados u otros usuarios externos. Esto es lo que obtiene con Sistema telefónico.

Al agregar el servicio Plan de llamadas, los empleados reciben un número de teléfono principal en Skype Empresarial. Pueden realizar llamadas telefónicas a números externos a la empresa o recibirlas de ellos. Pueden realizar llamadas de voz entre teléfonos VoIP, equipos y dispositivos móviles. En caso de emergencia, pueden llamar al 911 para obtener ayuda.

Si desea ver instrucciones detalladas para la configuración, vea Configurar Planes de llamadas.

### <a name="set-up-skype-meeting-broadcast"></a>Configurar la Difusión de reunión de Skype

Difusión de reunión de Skype es una característica que le permite producir, hospedar y difundir reuniones con hasta 10 000 asistentes. **Para obtener más información sobre cómo funciona, vea [¿Qué es una Difusión de reunión de Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**.

A continuación se muestra una introducción a los pasos para configurar Difusión de reunión de Skype:

1. [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): asigne licencias de **Skype Empresarial Online** o **Enterprise Plan** a todo aquel que vaya a **hospedar** una reunión de difusión.

2. [Habilitar la Difusión de reunión de Skype](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): esta característica no está habilitada de forma predeterminada. Una vez activado, los usuarios podrán hospedar reuniones de difusión con otras personas de la organización.

3. [Configurar la red para Difusión de reunión de Skype](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): si quiere hospedar seminarios web u otras difusiones con asistentes que no pertenecen a su empresa, debe configurar la red.

4. [Programar una Difusión de reunión de Skype](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) y pedir a un [Unirse a una Difusión de reunión de Skype](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): asegúrese de que las reuniones de difusión funcionen programando una Difusión de reunión de Skype en  *https://portal.broadcast.skype.com*  y haciendo que alguien pruebe a unirse a ella.

## <a name="learn-about-network-connectivity-requirements"></a>Más información sobre los requisitos de conectividad de red
<a name="bkmk_more"> </a>

La calidad de audio, vídeo y uso compartido de la aplicación en Skype Empresarial se ve enormemente afectada por la calidad de la conectividad de red de punto a punto Para una experiencia óptima, es importante asegurarse de que exista una conexión de buena calidad entre la red de la empresa y Skype Empresarial Online. Para obtener información sobre red y optimización, vea [Optimización del rendimiento de Skype Empresarial Online](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>¿Ha terminado la configuración? Introducción a Skype Empresarial
<a name="bkmk_more"> </a>

[Capacitación de Skype Empresarial](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): ¡echa un vistazo a esta lista de temas de capacitación para ayudarte a empezar rápidamente!

[Iniciar una llamada de conferencia de Skype Empresarial](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[Configurar las opciones de los dispositivos de vídeo en Skype Empresarial](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[Realizar y recibir una videollamada con Skype Empresarial](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Temas relacionados
<a name="bkmk_more"> </a>

[Planificar la conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
