---
title: Expansor de configuración General Front-End de Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Para editar las propiedades del grupo de servidores Front-End o de servidor Front-End, edición o configurar los siguientes atributos. La página de configuración se divide en las secciones siguientes:'
ms.openlocfilehash: 3af82a83afe27ce06a3c41f881154c2850cad521
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374205"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Expansor de configuración General Front-End de Lync Server 2010

Para editar las propiedades del grupo de servidores Front-End o de servidor Front-End, edición o configurar los siguientes atributos. La página de configuración se divide en las secciones siguientes:

 **General**

- **FQDN**: el nombre de dominio completo del grupo de servidores Front-End o de servidor Front-End.

- Seleccione **usar todas las direcciones IP configuradas** para hacer uso de todas las direcciones configuradas en el grupo de servidores Front-End o de servidor Front-End.

    > [!IMPORTANT]
    > No debe seleccionar esta opción si instala el servidor de mediación en el servidor Front-End o un grupo de servidores Front-End. Los servidores de mediación y servidores Front-End necesitan las direcciones IP dedicadas en el que desea comunicarse.

- Seleccione **limitar el uso del servicio a las direcciones IP seleccionadas** y escriba la dirección IP para la **dirección IP principal** para la comunicación de grupo de servidores Front-End o de servidor Front-End con el resto de la implementación. En **dirección IP de RTC** , escriba la dirección IP que está asociada con el servidor de mediación.

    **Características y funciones**

- **Conferencia**: seleccione la casilla de verificación si desea que las características de conferencia en su implementación. Las conferencias incluyen audio, vídeo, uso compartido de aplicaciones, uso compartido de escritorio y conferencias Web. Debe crear y asociar un servidor Office Web Apps para las conferencias Web (definida más adelante en esta página de propiedades).

- Si ha seleccionado conferencias, puede seleccionarse la **conferencia de acceso telefónico local (RTC)** . Active la casilla de verificación para habilitar las características de conferencia de acceso telefónico.

- Seleccione la casilla de verificación **Enterprise Voice** si va a implementar las características para habilitar Lync Server 2013 para que actúe como su sistema de teléfono de voz mediante voz a través de tecnologías IP (VoIP), incluida la opción de implementación de teléfonos auriculares, SIP troncos o público conectividad de red telefónica conmutada con el servidor de mediación, puertas de enlace RTC y IP-PBX, en combinación o solo, basándose en los requisitos y el diseño. Para ver todos los detalles en Enterprise Voice, vea [Enterprise Voice](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) y [planeación para Enterprise Voice en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Asociaciones**

- **Almacén de SQL Server**: el FQDN de SQL Server (y, opcionalmente, una instancia con nombre) asociada con el grupo de servidores Front-End o de servidor Front-End. Seleccione el almacén de SQL Server en la lista o crear un nuevo almacén de SQL Server haciendo clic en **nuevo**

- **Almacén de archivo**: seleccione el FQDN del servidor y el recurso compartido (en el formato `\\<FQDN of server>\<share name>`) que van a actuar como la ubicación del almacén de archivo para los archivos compartidos que Lync Server 2013 crea y usa para la replicación de directorios de conferencia y otros fines. Seleccione el almacén de archivos de la lista o crear un nuevo almacén de archivos haciendo clic en **nuevo**.

- Seleccione la casilla de verificación de **Asociar el servidor de archivado** para habilitar a un servidor de archivado para este grupo de servidores Front-End o de servidor Front-End. Después de seleccionar la casilla de verificación, seleccione un servidor de archivado existente de la lista o haga clic en **nuevo** para crear las definiciones de un nuevo servidor de archivado.

- Seleccione la casilla de verificación de **Asociar el servidor de supervisión** para habilitar a un servidor de supervisión para este grupo de servidores Front-End o de servidor Front-End. Después de seleccionar la casilla de verificación, seleccione un servidor de supervisión existente de la lista o haga clic en **nuevo** para crear las definiciones de un nuevo servidor de supervisión.

- Seleccione el **asociar grupo de servidores perimetrales (para componentes multimedia** casilla de verificación para habilitar un servidor perimetral para este grupo de servidores Front-End o de servidor Front-End. Después de seleccionar la casilla de verificación, seleccione un servidor perimetral existente o un grupo de servidores de la lista o haga clic en **nuevo** para crear las definiciones de un nuevo servidor perimetral o grupo de servidores.

  **Resistencia**

- Seleccione la casilla de verificación **grupo de registrador de copia de seguridad asociado** a en la lista Seleccione un grupo de servidores Front-End o de servidor Front-End que será el registrador de copia de seguridad (es decir, al servidor Front-End o Front-End al grupo designado como un registrador secundario en caso de que la principal se produce un error)

- Si ha seleccionado grupo de registrador de copia de seguridad de asociado y ha elegido a un registrador de reserva, puede seleccionar la casilla de verificación para **conmutación por error automática y la conmutación por recuperación de Voice**. Ahora puede definir propiedades numéricas para **detección interno voz de conmutación por error (s)** y un **intervalo de la conmutación por recuperación de Voice (seg.)**. Para obtener información detallada, consulte [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Servicios Web**

- Para configurar **los servicios web internos**, puede definir **puertos de escucha** para **HTTP** y **HTTPS**. De forma predeterminada, estos son el puerto TCP 80 y el puerto TCP 443, respectivamente. También se pueden configurar los **puertos publicados** para **HTTP** y **HTTPS**. De forma predeterminada, estos son el puerto TCP 80 y el puerto TCP 443, respectivamente. En función de la configuración de servicios web internos y el uso de equilibradores de carga (equilibradores de carga de hardware y equilibrio de carga DNS), ajuste los valores de puerto para definir el proceso de escucha y los puertos publicados.

    > [!IMPORTANT]
    > Servicios web internos y escucha definido y puertos publicados son para dispositivos y clientes internos. Dispositivos y clientes externos usen los servicios web externos de escucha y publica los puertos, junto con el nombre de dominio completo de servicios web externos definido (FQDN).

- Para configurar **los servicios web externos**, es posible definir **puertos de escucha** para **HTTP** y **HTTPS**. De forma predeterminada, estos son el puerto TCP 80 y el puerto TCP 443, respectivamente. También se pueden configurar los **puertos publicados** para **HTTP** y **HTTPS**. De forma predeterminada, estos son el puerto TCP 80 y el puerto TCP 443, respectivamente. En función de la configuración de servicios web internos y el uso de equilibradores de carga (equilibradores de carga de hardware y equilibrio de carga DNS), ajuste los valores de puerto para definir el proceso de escucha y los puertos publicados.

    > [!IMPORTANT]
    > Servicios web externos y escucha definido y puertos publicados son para los dispositivos y los clientes externos. Los dispositivos y los clientes externos usen los servicios web externos de escucha y publicado puertos, normalmente definidos por el proxy inverso junto con el nombre de dominio completo de servicios web externos definido (FQDN). La relación de los servicios web externos FQDN y las direcciones URL sencillas definen las direcciones de (dirección URL) del localizador uniforme de recursos que va a usar los clientes externos para tener acceso a los servicios disponibles para los usuarios externos y dispositivos. Para obtener más detalles sobre las direcciones URL sencillas, consulte [Planning for Simple URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).

  **Servidor de mediación**

- Para configurar las propiedades del **Servidor de mediación** para un servidor de mediación combinado (es decir, un servidor de mediación implementados en el grupo de servidores Front-End o de servidor Front-End), seleccione el **servidor de mediación combinado habilitado**.

- Para definir los **puertos de escucha** para un servidor de mediación combinado, escriba el valor **TLS** y **TCP** del puerto que escucha el servidor de mediación combinado. De forma predeterminada, TLS se define como el puerto TCP 5067.

- Para definir un valor de puerto TCP para el servidor de mediación, seleccione la casilla de verificación **Habilitar el puerto TCP** . De forma predeterminada, el servidor de mediación usa la seguridad de la capa de transporte (TLS) a través del protocolo TCP. Puertos TCP están disponibles sólo cuando está habilitada la selección de habilitar el puerto TCP.

    > [!NOTE]
    > Ésta es una configuración opcional, y se debe hacer referencia a los requisitos de la puerta de enlace o RTC para determinar si necesita. El valor de este puerto es 5068 de forma predeterminada.

- Definir troncos que están asociados con el servidor de mediación combinado. Si ya ha definido troncos, se podrán asociar inmediatamente con el servidor de mediación.

    Si tiene más de una puerta de enlace asociada con un servidor de mediación, puede especificar la puerta de enlace predeterminada seleccionando la puerta de enlace que se desea establecer como predeterminada y, al hacer clic en **Establecer como predeterminado**. Si decide quitar la puerta de enlace predeterminada actual, seleccione la puerta de enlace y haga clic en **Unmake predeterminado**.

> [!IMPORTANT]
> Si realiza cambios en las propiedades de este cuadro de diálogo, debe publicar la topología y ejecute la Skype para el Asistente para la implementación de servidor de negocio en todos los servidores afectados. Después de publicar la nueva topología, se proporciona una lista de servidores afectados donde se debe ejecutar el Skype para el Asistente para la implementación de servidor de negocio para usted como un vínculo en la pantalla de resumen de publicación correcta de topología. Para obtener información detallada sobre la publicación de la topología actualizada, consulte [publicar la topología](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Para obtener información detallada sobre la Skype para el Asistente para la implementación de servidor de negocio, vea [Lync Server Administrative Tools](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx).

Haga clic en **Aceptar** para guardar y confirmar los cambios en el documento de topología.

Haga clic en **Cancelar** para descartar los cambios y cerrar la **Editar propiedades** para el grupo de servidores Front-End o de servidor Front-End.

Haga clic en **Ayuda** para leer este tema de ayuda.

## <a name="see-also"></a>Vea también

[Definir y configurar un servidor Standard Edition o grupo de servidores Front-End](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)