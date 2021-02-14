---
title: Implementar calidad de servicio (QoS) en clientes de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Obtenga información sobre cómo usar Calidad de servicio (QoS) para optimizar el tráfico de red del cliente de escritorio de Microsoft Teams.
localization_priority: Normal
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
ms.openlocfilehash: bc352303cf63ea966927aece0aef36854a0ace1b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526407"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Implementar calidad de servicio (QoS) en clientes de Microsoft Teams

Puede usar QoS (Calidad de servicio) basada en directivas en la directiva de grupo para establecer el intervalo de puertos de origen para el valor de DSCP predefinido en el cliente de Teams. Los intervalos de puertos especificados en la tabla siguiente son un punto de partida para crear una directiva para cada carga de trabajo.

*Tabla 1. Intervalos de puertos iniciales recomendados*

|Tipo de tráfico de medios | Rango de puertos de origen del cliente  |Protocolo|Valor de DSCP|Clase DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50 000 – 50 019|TCP/UDP|46|Desvío rápido (EF)|
|Vídeo| 50 020 – 50 039|TCP/UDP|34|Desvío garantizado (AF41)|
|Aplicación/Compartir pantalla| 50 040 – 50 059|TCP/UDP|18|Desvío garantizado (AF21)|
| | | | | |

Siempre que sea posible, configure las opciones de QoS basadas en directivas dentro de un objeto de directiva de grupo. Los pasos siguientes son muy similares a la configuración de intervalos de puertos y una directiva de calidad de servicio para sus clientes en Skype Empresarial  [Server,](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)que tiene algunos detalles adicionales que puede que no sean necesarios.

Para crear una directiva de audio de QoS para equipos Windows 10 unidos a un dominio, primero inicie sesión en un equipo en el que se haya instalado la administración de directivas de grupo. Abra la administración de directivas de grupo (haga clic en Inicio, seleccione Herramientas administrativas y, a continuación, haga clic en Administración de directivas de grupo) y, después, siga estos pasos:

1. En Administración de directivas de grupo, busque el contenedor donde debe crearse la nueva directiva. Por ejemplo, si todos los equipos cliente se encuentran en una UO denominada **Clientes,** la nueva directiva debe crearse en la UO Clientes.

1. Haga clic con el botón secundario en el contenedor adecuado y, a continuación, haga clic en Crear un GPO en este **dominio y vincóquelo aquí.**

1. En el **cuadro de diálogo Nuevo GPO,** escriba un  nombre para el nuevo objeto de directiva de grupo en el cuadro Nombre y, a continuación, haga clic en **Aceptar.**

1. Haga clic con el botón derecho en la directiva recién creada y, a continuación, haga clic **en Editar.**

1. En el Editor de administración de directivas de grupo, expanda Configuración del **equipo,** Configuración de **Windows,** Haga clic con el botón derecho en **QoS** basada en directiva y, a continuación, haga clic **en Crear nueva directiva.**

1. En el **cuadro de diálogo QoS** basado en directivas, en la página de apertura, escriba un nombre para la nueva directiva en el **cuadro** Nombre. Seleccione **Especificar valor de DSCP** y establezca el valor en **46.** Deje **la opción "Especificar velocidad de limitación** de salida" no seleccionada y, a continuación, haga clic **en Siguiente.**

1. En la página siguiente, seleccione Solo las aplicaciones con este nombre **ejecutable,** escriba el nombre **Teams.exe** y, a continuación, haga clic en **Siguiente.** Esta configuración indica a la directiva que solo priorice el tráfico de coincidencia desde el cliente de Teams.

1. En la tercera página, asegúrese de seleccionar Cualquier dirección **IP** de origen y Cualquier **dirección IP** de destino y, a continuación, haga clic en **Siguiente.** Estas dos configuraciones garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que envió los paquetes y del equipo (dirección IP) que recibirán los paquetes.

1. En la página cuatro, seleccione **TCP y UDP** en el seleccionar el protocolo que esta directiva de **QoS aplica a** la lista desplegable. TCP (Protocolo de control de transmisión) y UDP (protocolo de datagramas de usuario) son los dos protocolos de red más usados.

1. En el encabezado **Especifique el número de puerto de origen,** seleccione Desde este puerto o rango de **origen.** En el cuadro de texto correspondiente, escriba el intervalo de puertos reservado para las transmisiones de audio. Por ejemplo, si ha reservado los puertos 50000 a través de los puertos 50019 para tráfico de audio, escriba el intervalo de puertos con este formato: **50000:50019.** Haga clic en **Finalizar**.

1. Repita los pasos del 5 al 10 para crear directivas de uso compartido de aplicaciones y vídeo, sustituyendo los valores apropiados en los pasos 6 y 10.

Las nuevas directivas que ha creado no efecto hasta que la directiva de grupo se actualice en los equipos cliente. Aunque la directiva de grupo se actualiza periódicamente por sí misma, puede forzar una actualización inmediata siguiendo estos pasos:

1. En cada equipo para el que quiera actualizar la directiva de grupo, abra un símbolo del sistema como administrador *(ejecutar como administrador).*

1. En el símbolo del sistema, escribe

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Comprobar marcas de DSCP en el objeto de directiva de grupo

Para comprobar que los valores del objeto de directiva de grupo se han establecido, realice los pasos siguientes:

1. Abrir un símbolo del sistema como administrador *(Ejecutar como administrador).*

1. En el símbolo del sistema, escribe

   ```console
   gpresult /R > gp.txt
   ```

   Esto generará un informe de los GPO aplicados y lo enviará a un archivo de texto denominado *gp.txt.*

   Para obtener un informe HTML más legible denominado *gp.html,* escriba el comando siguiente:

   ```console
   gpresult /H gp.html
   ```

1. En el archivo generado, busque el encabezado **Objetos** de directiva de grupo aplicados y compruebe que los nombres de los objetos de directiva de grupo creados anteriormente están en la lista de directivas aplicadas.

1. Abra el Editor del Registro y vaya a

   Directivas de software DE MÁQUINA LOCAL de HKEY \_ \_ para \\ \\ \\ \\ \\ QoS de Microsoft Windows

   Compruebe los valores de las entradas del Registro enumeradas en la tabla 2.

   *Tabla 2. Valores de las entradas del registro de Windows para QoS*

   |          Nombre          |  Tipo  |    Datos     |
   |         :---:          | :---:  |    :---:    |
   |    Nombre de la aplicación    | REG_SZ |  Teams.exe  |
   |       Valor de DSCP       | REG_SZ |     46      |
   |        IP local        | REG_SZ |     \*      |
   | Longitud del prefijo de IP local | REG_SZ |     \*      |
   |       Puerto local       | REG_SZ | 50000-50019 |
   |        Protocolo        | REG_SZ |     \*      |
   |       IP remota        | REG_SZ |     \*      |
   |    Prefijo IP remoto    | REG_SZ |     \*      |
   |      Puerto remoto       | REG_SZ |     \*      |
   |     Velocidad de limitación      | REG_SZ |     -1      |
   | | | |

1. Compruebe que el valor de la entrada de nombre de aplicación es correcto para el cliente que está usando y compruebe que las entradas de valor de DSCP y puerto local reflejen la configuración en el objeto de directiva de grupo.


## <a name="related-topics"></a>Temas relacionados

[Implementar calidad de servicio (QoS) en Teams](QoS-in-Teams.md)