---
title: Implementar calidad de servicio (QoS) en clientes de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Obtenga información sobre cómo usar la Calidad de servicio (QoS) para optimizar el tráfico de red para el cliente de escritorio de Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 70dbc5794fe64a1afed86bc82d0005ad7d510c5f
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563928"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Implementar calidad de servicio (QoS) en clientes de Microsoft Teams

Puede usar la Calidad de servicio (QoS) basada en directivas en directiva de grupo para establecer el intervalo de puertos de origen para el valor de DSCP predefinido en el cliente de Teams. Los intervalos de puertos especificados en la tabla siguiente son un punto de partida para crear una directiva para cada carga de trabajo.

*Tabla 1. Intervalos de puertos iniciales recomendados*

|Tipo de tráfico de medios | Rango de puertos de origen del cliente  |Protocolo|Valor de DSCP|Clase DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50 000 – 50 019|TCP/UDP|46|Desvío rápido (EF)|
|Vídeo| 50 020 – 50 039|TCP/UDP|34|Desvío garantizado (AF41)|
|Aplicación/Compartir pantalla| 50 040 – 50 059|TCP/UDP|18|Desvío garantizado (AF21)|
| | | | | |

Siempre que sea posible, configure las opciones de QoS basadas en directivas en un objeto de directiva de grupo. Los pasos siguientes son muy similares a [La configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes en Skype Empresarial Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), que tiene algunos detalles adicionales que puede que no sean necesarios.

Para crear una directiva de audio de QoS para equipos Windows 10 unidos a un dominio, primero inicie sesión en un equipo en el que se haya instalado la administración de directiva de grupo. Abre administración de directiva de grupo (haz clic en Inicio, selecciona Herramientas administrativas y, a continuación, haz clic en Administración de directiva de grupo) y completa los pasos siguientes:

1. En administración de directiva de grupo, busque el contenedor donde se debe crear la nueva directiva. Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada **Clientes**, la nueva directiva debe crearse en la unidad organizativa clientes.

1. Haga clic con el botón secundario en el contenedor adecuado y, a continuación, haga clic **en Crear un GPO en este dominio y vincularlo aquí**.

1. En el cuadro de diálogo **Nuevo GPO**, escriba un nombre para el nuevo objeto directiva de grupo en el cuadro **Nombre** y, a continuación, haga clic en **Aceptar**.

1. Haga clic con el botón secundario en la directiva recién creada y, a continuación, haga clic en **Editar**.

1. En el Editor de administración de directiva de grupo, expanda **Configuración del equipo**, expanda **Configuración de Windows**, haga clic con el botón derecho en **QoS basado en** directivas y, a continuación, haga clic en **Crear nueva directiva**.

1. En el cuadro de diálogo **QoS basado** en directivas, en la página de apertura, escriba un nombre para la nueva directiva en el cuadro **Nombre** . Seleccione **Especificar valor DSCP** y establezca el valor en **46**. Deje **no seleccionado Especificar velocidad de limitación saliente** y, a continuación, haga clic en **Siguiente**.

1. En la página siguiente, seleccione **Solo las aplicaciones con este nombre ejecutable** , escriba el nombre **Teams.exe** y, a continuación, haga clic en **Siguiente**. Esta configuración indica a la directiva que solo priorice el tráfico coincidente del cliente de Teams.

1. En la tercera página, asegúrese de que están seleccionadas las opciones **Cualquier dirección IP de origen** y **Cualquier dirección IP de destino** y, a continuación, haga clic en **Siguiente**. Estas dos configuraciones garantizan que los paquetes se administren independientemente del equipo (dirección IP) que envió los paquetes y qué equipo (dirección IP) recibirá los paquetes.

1. En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo que esta directiva de QoS aplica a** . TCP (Transmission Control Protocol) y UDP (User Datagram Protocol) son los dos protocolos de red más usados.

1. En el encabezado **Especifique el número de puerto de origen**, seleccione **Desde este puerto o rango de origen**. En el cuadro de texto correspondiente, escribe el intervalo de puertos reservado para las transmisiones de audio. Por ejemplo, si ha reservado los puertos 50000 a través de los puertos 50019 para el tráfico de audio, introduzca el intervalo de puertos con este formato: **50000:50019**. Haga clic en **Finalizar**.

1. Repita los pasos 5 a 10 para crear directivas para uso compartido de aplicaciones y vídeos y escritorios, sustituyéndolos por los valores adecuados en los pasos 6 y 10.

Las nuevas directivas que ha creado no se aplicarán hasta que se actualice directiva de grupo en los equipos cliente. Aunque directiva de grupo se actualiza periódicamente por sí mismo, puede forzar una actualización inmediata siguiendo estos pasos:

1. En cada equipo para el que quiera actualizar directiva de grupo, abra un símbolo del sistema como administrador (*Ejecutar como administrador*).

1. En el símbolo del sistema, escribe

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Comprobar el marcado de DSCP en el objeto directiva de grupo

Para comprobar que se han establecido los valores del objeto directiva de grupo, siga estos pasos:

1. Abrir un símbolo del sistema como administrador (*Ejecutar como administrador*).

1. En el símbolo del sistema, escribe

   ```console
   gpresult /R > gp.txt
   ```

   Esto generará un informe de los GPO aplicados y lo enviará a un archivo de texto denominado *gp.txt*.

   Para obtener un informe HTML más legible denominado *gp.html*, escriba el siguiente comando:

   ```console
   gpresult /H gp.html
   ```

1. En el archivo generado, busque el encabezado **Objetos directiva de grupo aplicados** y compruebe que los nombres de los objetos directiva de grupo creados anteriormente están en la lista de directivas aplicadas.

1. Abre el Editor del Registro y ve a

   Directivas de software HKEY\_LOCAL\_MACHINE\\de\\\\Microsoft\\Windows\\QoS

   Compruebe los valores de las entradas del Registro enumeradas en la Tabla 2.

   *Tabla 2. Valores de las entradas del Registro de Windows para QoS*

   |          Nombre          |  Tipo  |    Datos     |
   |         :---:          | :---:  |    :---:    |
   |    Nombre de la aplicación    | REG_SZ |  Teams.exe  |
   |       Valor de DSCP       | REG_SZ |     46      |
   |        IP local        | REG_SZ |     \*      |
   | Longitud del prefijo de IP local | REG_SZ |     \*      |
   |       Puerto local       | REG_SZ | 50000-50019 |
   |        Protocolo        | REG_SZ |     \*      |
   |       IP remota        | REG_SZ |     \*      |
   |    Prefijo ip remoto    | REG_SZ |     \*      |
   |      Puerto remoto       | REG_SZ |     \*      |
   |     Velocidad de limitación      | REG_SZ |     -1      |
   | | | |

1. Compruebe que el valor de la entrada Nombre de aplicación es correcto para el cliente que está usando y compruebe que las entradas Valor de DSCP y Puerto local reflejen la configuración del objeto directiva de grupo.


## <a name="related-topics"></a>Temas relacionados

[Implementar la calidad de servicio (QoS) en Teams](QoS-in-Teams.md)