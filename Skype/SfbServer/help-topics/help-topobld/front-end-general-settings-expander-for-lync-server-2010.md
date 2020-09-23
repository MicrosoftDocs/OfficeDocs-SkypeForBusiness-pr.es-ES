---
title: Expansor de configuración general front-end para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Para editar las propiedades del servidor front-end o del grupo de servidores front-end, edite o configure los siguientes atributos. La página de configuración consta de las secciones siguientes:'
ms.openlocfilehash: 6d7cdb9067ff88b383077538e38c39c2f8e86a5a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219101"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Expansor de configuración general front-end para Lync Server 2010

Para editar las propiedades del servidor front-end o del grupo de servidores front-end, edite o configure los siguientes atributos. La página de configuración consta de las secciones siguientes:

 **General**

- **FQDN**: el nombre de dominio completo del servidor front-end o del grupo de servidores front-end.

- Seleccione **usar todas las direcciones IP configuradas** para usar todas las direcciones configuradas en el servidor front-end o el grupo de servidores front-end.

    > [!IMPORTANT]
    > No debe seleccionar esta opción si combinar el servidor de mediación en el servidor front-end o en el grupo de servidores front-end. Los servidores de mediación y los servidores front-end necesitan direcciones IP dedicadas en las que comunicarse.

- Seleccione **limitar el uso del servicio a las direcciones IP seleccionadas** y escriba la dirección IP para la **dirección IP principal** del servidor front-end o la comunicación del grupo de servidores front-end con el resto de la implementación. Escriba la dirección IP de **RTC** que está asociada con el servidor de mediación.

    **Características y funcionalidad**

- **Conferencia**: seleccione esta casilla de verificación si desea tener características de conferencia en la implementación. La conferencia incluye, audio, vídeo, recurso compartido de aplicaciones y escritorio y conferencia web. Tendrá que crear y asociar un servidor de Office Web Apps para conferencias web (definido más adelante en esta página de propiedades).

- Si ha seleccionado Conferencia, puede seleccionar **Conferencia de acceso telefónico local (RTC)**. Seleccione la casilla de verificación para habilitar las características de conferencia de acceso telefónico local.

- Seleccione la casilla **telefonía IP empresarial** si tiene previsto implementar características para permitir que Lync Server 2013 funcione como sistema de voz telefónica mediante tecnologías de voz sobre IP (VoIP), incluida la opción de implementar teléfonos móviles, troncos SIP o conectividad de red telefónica conmutada pública mediante el uso del servidor de mediación, las puertas de enlace RTC y el IP-PBX, en combinación o en los requisitos. Para obtener información detallada sobre la telefonía IP empresarial, consulte [Enterprise Voice](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) y [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Asociaciones**

- **Almacén de SQL Server**: el FQDN de SQL Server (y, opcionalmente, una instancia con nombre) asociado con el servidor front-end o el grupo de servidores front-end. Seleccione el almacén SQL Server de la lista o cree un nuevo almacén SQL Server haciendo clic en **Nuevo**

- **Almacén de archivos**: seleccione el FQDN del servidor y el recurso compartido (en el formato  `\\<FQDN of server>\<share name>` ) que actuará como la ubicación del almacén de archivos para los archivos compartidos que Lync Server 2013 crea y usa para la replicación, los directorios de conferencia y otros fines. Seleccione el almacén de archivos de la lista o cree un nuevo almacén de archivos haciendo clic en **Nuevo**.

- Active la casilla **asociar servidor de archivado** para habilitar un servidor de archivado para este servidor front-end o grupo de servidores front-end. Después de seleccionar la casilla, seleccione un servidor de archivado existente de la lista o haga clic en **nuevo** para crear las definiciones de un nuevo servidor de archivado.

- Seleccione la casilla **asociar servidor de supervisión** para habilitar un servidor de supervisión para este servidor front-end o grupo de servidores front-end. Después de seleccionar la casilla de verificación, seleccione un servidor de supervisión existente de la lista o haga clic en **nuevo** para crear las definiciones de un nuevo servidor de supervisión.

- Seleccione la casilla **asociar grupo de servidores perimetrales (para componentes multimedia** para habilitar un servidor perimetral para este servidor front-end o grupo de servidores front-end. Después de seleccionar la casilla, seleccione un servidor perimetral o un grupo de servidores perimetral existente de la lista o haga clic en **nuevo** para crear las definiciones para un nuevo servidor perimetral o un grupo de servidores perimetrales.

  **Resistencia**

- Active la casilla de verificación **grupo de registradores de reserva asociado** para seleccionar de la lista un servidor front-end o un grupo de servidores front-end que será el registrador de reserva (es decir, el servidor front-end o el grupo de servidores front-end designado como registrador secundario en el caso de que se produzca un error en el principal)

- Si selecciona Grupo asociado de registradores de copia de seguridad y ha elegido un registrador de copia de seguridad, puede marcar la casilla de verificación **Conmutación por error automática y conmutación por recuperación para voz**. Ahora puede definir propiedades numéricas para **Detección interna de conmutación por error de voz (seg)** y **Intervalo de conmutación por recuperación de voz (seg)**. Para más información, consulte [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Servicios web**

- Para configurar los **Servicios web internos**, defina los **Puertos de escucha** de **HTTP** y **HTTPS**. De forma predeterminada son puerto TCP 80 y puerto TCP 443, respectivamente. Configure también los **Puertos publicados** para **HTTP** y **HTTPS**. De forma predeterminada son puerto TCP 80 y puerto TCP 443, respectivamente. En función de la configuración de los servicios web internos y el uso de equilibradores de carga (equilibradores de carga de hardware y equilibradores de carga de DNS), ajuste los valores de puerto para definir los puertos de escucha y los puertos publicados.

    > [!IMPORTANT]
    > Los servicios web internos y los puertos definidos de escucha y publicados son para dispositivos y clientes internos. Los dispositivos y clientes externos utilizan los puertos de escucha y publicados de los servicios web externos junto con el nombre de dominio completo (FQDN) de los servicios web externos definidos.

- Para configurar los **Servicios web externos**, defina los **Puertos de escucha** para **HTTP** y **HTTPS**. De forma predeterminada son puerto TCP 80 y puerto TCP 443, respectivamente. Configure también los **Puertos publicados** para **HTTP** y **HTTPS**. De forma predeterminada son puerto TCP 80 y puerto TCP 443, respectivamente. En función de la configuración de los servicios web internos y el uso de equilibradores de carga (equilibradores de carga de hardware y equilibradores de carga de DNS), ajuste los valores de puerto para definir los puertos de escucha y los puertos publicados.

    > [!IMPORTANT]
    > Los servicios web externos y los puertos definidos de escucha y publicados son para dispositivos y clientes externos. Los dispositivos y clientes externos utilizan los puertos de escucha y publicados de los servicios web externos, generalmente definidos por el proxy inverso junto con el nombre de dominio completo (FQDN) de los servicios web externos definidos. La relación del FQDN de los servicios web externos y las Direcciones URL simples define las direcciones del localizador uniforme de recursos (URL) que utilizarán los clientes externos para acceder a los servicios disponibles para los dispositivos y usuarios externos. Para más información sobre las Direcciones URL simples, consulte [Planning for Simple URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).

  **Servidor de mediación**

- Para configurar las propiedades del **servidor** de mediación de un servidor de mediación combinado (es decir, un servidor de mediación implementado en el servidor front-end o el grupo de servidores front-end), seleccione **servidor de mediación combinado habilitado**.

- Para definir los **puertos de escucha** de un servidor de mediación combinado, escriba el valor del puerto **TCP** y de **TLS** en el que escucha el servidor de mediación combinado. De forma predeterminada, TLS está definido como puerto TCP 5067.

- Para definir un valor de puerto TCP para el servidor de mediación, active la casilla **Habilitar puerto TCP** . De forma predeterminada, el servidor de mediación usa la seguridad de la capa de transporte (TLS) a través del protocolo TCP. Los puertos TCP solamente están disponible cuando la selección Habilitar puerto TCP está habilitada.

    > [!NOTE]
    > Se trata de una configuración opcional y deberá consultar los requisitos de su puerta de enlace o RTC para asegurarse de si es necesaria. De forma predeterminada, el valor del puerto TCP es 5068.

- Defina los troncos que se asocian con el servidor de mediación colocado. Si ya ha definido troncos, éstos se podrán asociar con el servidor de mediación.

    Si tiene más de una puerta de enlace asociada a un servidor de mediación, puede especificar la puerta de enlace predeterminada seleccionando la puerta de enlace que desee establecer como predeterminada y haciendo clic en **convertir en predeterminada**. Si decide eliminar la puerta de enlace que actualmente es la predeterminada, selecciónela y haga clic en **Eliminar predeterminado**.

> [!IMPORTANT]
> Si realiza cambios en las propiedades de este cuadro de diálogo, debe publicar la topología y ejecutar el Asistente para la implementación de Skype empresarial Server en todos los servidores afectados. Después de publicar la nueva topología, se proporciona una lista de los servidores afectados en los que se debe ejecutar el Asistente para la implementación de Skype empresarial Server como un vínculo en la pantalla de Resumen de publicación de topología correcta. Para más información sobre la topología actualizada, consulte [Publish the Topology](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Para obtener más información sobre el Asistente para la implementación de Skype empresarial Server, consulte [herramientas administrativas de Lync Server](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx).

Haga clic en **Aceptar** para guardar y confirmar los cambios en el documento de la topología.

Haga clic en **Cancelar** para descartar los cambios y cerrar las **propiedades de edición** para el servidor front-end o el grupo de servidores front-end.

Haga clic en **Ayuda** para leer este tema de la ayuda.

## <a name="see-also"></a>Vea también

[Definir y configurar un grupo de servidores front-end](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
