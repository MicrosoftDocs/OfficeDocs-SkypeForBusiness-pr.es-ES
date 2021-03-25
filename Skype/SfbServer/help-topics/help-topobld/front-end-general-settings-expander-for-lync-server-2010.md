---
title: Expansor de configuración general front-end para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Las propiedades del servidor front-end o del grupo de servidores front-end se modifican o configuran los atributos siguientes. La página de configuración consta de las secciones siguientes:'
ms.openlocfilehash: 63c784cbd254decdb108d8d8408cd01ef44657a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118629"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Expansor de configuración general front-end para Lync Server 2010

Las propiedades del servidor front-end o del grupo de servidores front-end se modifican o configuran los atributos siguientes. La página de configuración consta de las secciones siguientes:

 **General**

- **FQDN:** el nombre de dominio completo del servidor front-end o grupo de servidores front-end.

- Seleccione **Usar todas las direcciones IP configuradas** para usar todas las direcciones configuradas en el servidor front-end o grupo de servidores front-end.

    > [!IMPORTANT]
    > No debe seleccionar esta opción si coloca el servidor de mediación en el servidor front-end o grupo de servidores front-end. Los servidores de mediación y los servidores front-end necesitan direcciones IP dedicadas para comunicarse.

- Seleccione **Limitar el uso del** servicio a las direcciones IP seleccionadas y escriba la dirección IP de la dirección **IP** principal para la comunicación entre el servidor front-end o el grupo de servidores front-end con el resto de la implementación. Escriba en **Dirección IP RTC la** dirección IP asociada al servidor de mediación.

    **Características y funcionalidad**

- **Conferencia**: seleccione esta casilla de verificación si desea tener características de conferencia en la implementación. La conferencia incluye, audio, vídeo, recurso compartido de aplicaciones y escritorio y conferencia web. Deberá crear y asociar una conferencia web de Office Web Apps Server (definida más adelante en esta página Propiedades).

- Si ha seleccionado Conferencia, puede seleccionar **Conferencia de acceso telefónico local (RTC)**. Seleccione la casilla de verificación para habilitar las características de conferencia de acceso telefónico local.

- Active la casilla **Telefonía IP empresarial** si desea implementar características para permitir que Lync Server 2013 actúe como su sistema de voz telefónico mediante tecnologías de voz sobre IP (VoIP), incluida la opción de implementar teléfonos de teléfono, troncos SIP o conectividad de red telefónica conmutada con servidor de mediación, puertas de enlace RTC e IP-PBX, en combinación o solo, según el diseño y los requisitos. Para obtener más información Telefonía IP empresarial, vea [Telefonía IP empresarial](/previous-versions/office/lync-server-2013/lync-server-2013-enterprise-voice) [y Plan for Telefonía IP empresarial in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Asociaciones**

- **SQL Server:** el FQDN de la SQL Server (y, opcionalmente, una instancia con nombre) asociada con el servidor front-end o el grupo de servidores front-end. Seleccione el almacén SQL Server de la lista o cree un nuevo almacén SQL Server haciendo clic en **Nuevo**

- **Almacén** de archivos: seleccione el FQDN del servidor y el recurso compartido (con el formato ) que actuará como la ubicación del almacén de archivos para los archivos compartidos que Lync Server 2013 crea y usa para replicación, directorios de conferencia y otros  `\\<FQDN of server>\<share name>` fines. Seleccione el almacén de archivos de la lista o cree un nuevo almacén de archivos haciendo clic en **Nuevo**.

- Active la **casilla Asociar servidor de archivado** para habilitar un servidor de archivado para este servidor front-end o grupo de servidores front-end. Después de activar la casilla, seleccione un servidor de  archivado existente de la lista o haga clic en Nuevo para crear las definiciones de un nuevo servidor de archivado.

- Active la **casilla Asociar servidor de supervisión** para habilitar un servidor de supervisión para este servidor front-end o grupo de servidores front-end. Después de activar la casilla, seleccione un servidor de  supervisión existente de la lista o haga clic en Nuevo para crear las definiciones de un nuevo servidor de supervisión.

- Active la casilla Asociar grupo de servidores **perimetrales (para** componentes multimedia para habilitar un servidor perimetral para este servidor front-end o grupo de servidores front-end. Después de activar la casilla, seleccione un servidor perimetral o  grupo existente de la lista o haga clic en Nuevo para crear las definiciones de un nuevo servidor perimetral o grupo de servidores.

  **Resistencia**

- Active  la casilla Grupo de registradores de copia de seguridad asociado para seleccionar en la lista un servidor front-end o grupo de servidores front-end que será el registrador de copia de seguridad ( es decir, el servidor front-end o grupo de servidores front-end designado como registrador secundario en caso de que el principal falle)

- Si selecciona Grupo asociado de registradores de copia de seguridad y ha elegido un registrador de copia de seguridad, puede marcar la casilla de verificación **Conmutación por error automática y conmutación por recuperación para voz**. Ahora puede definir propiedades numéricas para **Detección interna de conmutación por error de voz (seg)** y **Intervalo de conmutación por recuperación de voz (seg)**. Para más información, consulte [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)

  **Servicios web**

- Para configurar los **Servicios web internos**, defina los **Puertos de escucha** de **HTTP** y **HTTPS**. De forma predeterminada son puerto TCP 80 y puerto TCP 443, respectivamente. Configure también los **Puertos publicados** para **HTTP** y **HTTPS**. De forma predeterminada son puerto TCP 80 y puerto TCP 443, respectivamente. En función de la configuración de los servicios web internos y el uso de equilibradores de carga (equilibradores de carga de hardware y equilibradores de carga de DNS), ajuste los valores de puerto para definir los puertos de escucha y los puertos publicados.

    > [!IMPORTANT]
    > Los servicios web internos y los puertos definidos de escucha y publicados son para dispositivos y clientes internos. Los dispositivos y clientes externos utilizan los puertos de escucha y publicados de los servicios web externos junto con el nombre de dominio completo (FQDN) de los servicios web externos definidos.

- Para configurar los **Servicios web externos**, defina los **Puertos de escucha** para **HTTP** y **HTTPS**. De forma predeterminada son puerto TCP 80 y puerto TCP 443, respectivamente. Configure también los **Puertos publicados** para **HTTP** y **HTTPS**. De forma predeterminada son puerto TCP 80 y puerto TCP 443, respectivamente. En función de la configuración de los servicios web internos y el uso de equilibradores de carga (equilibradores de carga de hardware y equilibradores de carga de DNS), ajuste los valores de puerto para definir los puertos de escucha y los puertos publicados.

    > [!IMPORTANT]
    > Los servicios web externos y los puertos definidos de escucha y publicados son para dispositivos y clientes externos. Los dispositivos y clientes externos utilizan los puertos de escucha y publicados de los servicios web externos, generalmente definidos por el proxy inverso junto con el nombre de dominio completo (FQDN) de los servicios web externos definidos. La relación del FQDN de los servicios web externos y las Direcciones URL simples define las direcciones del localizador uniforme de recursos (URL) que utilizarán los clientes externos para acceder a los servicios disponibles para los dispositivos y usuarios externos. Para más información sobre las Direcciones URL simples, consulte [Planning for Simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls).

  **Servidor de mediación**

- Para **configurar** las propiedades del servidor de mediación para un servidor de mediación instalado (es decir, un servidor de mediación implementado en el servidor front-end o grupo de servidores front-end), seleccione Servidor de mediación instalado **habilitado**.

- Para definir los **puertos** de escucha de un servidor de mediación con colocación, escriba el valor de puerto **TLS** y **TCP** en el que escucha el servidor de mediación. De forma predeterminada, TLS está definido como puerto TCP 5067.

- Para definir un valor de puerto TCP para el servidor de mediación, active la casilla Habilitar puerto **TCP.** De forma predeterminada, el servidor de mediación usa la seguridad de la capa de transporte (TLS) sobre el protocolo TCP. Los puertos TCP solamente están disponible cuando la selección Habilitar puerto TCP está habilitada.

    > [!NOTE]
    > Se trata de una configuración opcional y deberá consultar los requisitos de su puerta de enlace o RTC para asegurarse de si es necesaria. De forma predeterminada, el valor del puerto TCP es 5068.

- Defina los troncos que se asocian con el servidor de mediación colocado. Si ya ha definido troncos, éstos se podrán asociar con el servidor de mediación.

    Si tiene más de una puerta de enlace asociada a un servidor de mediación, puede especificar la puerta de enlace predeterminada seleccionando la puerta de enlace que desea establecer como predeterminada y haciendo clic en **Hacer** predeterminado . Si decide eliminar la puerta de enlace que actualmente es la predeterminada, selecciónela y haga clic en **Eliminar predeterminado**.

> [!IMPORTANT]
> Si realiza cambios en las propiedades de este cuadro de diálogo, debe publicar la topología y ejecutar el Asistente para la implementación de Skype Empresarial Server en todos los servidores afectados. Después de publicar la nueva topología, se proporciona una lista de servidores afectados donde debe ejecutarse el Asistente para la implementación de Skype Empresarial Server como vínculo en la pantalla de resumen de publicación de topología correcta. Para más información sobre la topología actualizada, consulte [Publish the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-topology). Para obtener más información sobre el Asistente para la implementación de Skype Empresarial Server, vea [Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-administrative-tools).

Haga clic en **Aceptar** para guardar y confirmar los cambios en el documento de la topología.

Haga **clic en** Cancelar para descartar los cambios y cerrar las propiedades **de** edición del servidor front-end o grupo de servidores front-end.

Haga clic en **Ayuda** para leer este tema de la ayuda.

## <a name="see-also"></a>Ver también

[Definir y configurar un grupo de servidores front-end](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)