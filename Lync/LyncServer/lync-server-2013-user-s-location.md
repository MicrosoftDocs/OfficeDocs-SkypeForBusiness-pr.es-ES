---
title: 'Lync Server 2013: Ubicación del usuario'
TOCTitle: Ubicación del usuario
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994073(v=OCS.15)
ms:contentKeyID: 52061763
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ubicación del usuario en Lync Server 2013

 

_**Última modificación del tema:** 2013-03-09_

El enrutamiento basado en ubicación utiliza las mismas regiones de red, los mismos sitios y las mismas subredes definidos en Lync Server y que utilizan E9-1-1, CAC y Omisión de medios para aplicar las restricciones del enrutamiento de llamadas y, así, evitar que se omitan los números de pago de RTC. La ubicación de los usuarios se determina a partir de la subred IP de los extremos de Lync desde los que se conecta el usuario. Cada subred IP está asociada a un sitio de red, y los sitios de red se agrupan en regiones de red definidas por el administrador. El enrutamiento basado en ubicación se exige en función del sitio de red del usuario.

Las reglas del enrutamiento basado en ubicación se aplican según el sitio de red, es decir, un determinado conjunto de reglas se aplicará a todos los extremos habilitados para el enrutamiento basado en ubicación que estén ubicados dentro del mismo sitio de red. Los administradores pueden aplicar el enrutamiento basado en ubicación a los sitios de red que lo necesiten.

Se pueden definir directivas de enrutamiento de voz en cada sitio de red, para que todos los usuarios ubicados en el sitio de red utilicen una puerta de enlace RTC concreta para llamar a números de teléfono de RTC. Estas directivas de enrutamiento de voz tendrán prioridad sobre el enrutamiento definido por la directiva de voz del usuario, cuando el usuario esté ubicado en un sitio de red habilitado para el enrutamiento basado en ubicación, y se evitará que las llamadas se redirijan a través de otras puertas de enlace RTC habilitadas para el enrutamiento basado en ubicación. Cuando un usuario de Lync realiza una llamada de RTC, la directiva de voz del usuario determina si el usuario tiene autorización para realizar la llamada. Si la directiva de voz del usuario permite que el usuario realice la llamada, el enrutamiento basado en ubicación determinará por qué puerta de enlace RTC deberá salir la llamada. El enrutamiento basado en ubicación lo determina a partir de la ubicación del usuario.

La ubicación de los usuarios se puede clasificar de las siguientes maneras:

  - El usuario está ubicado en un sitio de red conocido y habilitado para el enrutamiento basado en ubicación, y su número de DID (Marcado entrante directo) finaliza en una puerta de enlace RTC situada en el mismo sitio de red (la oficina). El enrutamiento de las llamadas salientes se realizará a través de la directiva de enrutamiento de voz del sitio de red en el que está ubicado el usuario. Las llamadas de RTC entrantes que reciba el usuario se redirigirán a los extremos ubicados en el mismo sitio de red que la puerta de enlace RTC.

  - El usuario está ubicado en un sitio de red conocido y diferente del sitio de red donde se encuentra la puerta de enlace RTC (es decir, el usuario viajó a otra oficina de la compañía). El enrutamiento de las llamadas salientes utilizará la directiva de enrutamiento de voz del sitio de red en el que está ubicado el usuario. Las llamadas de RTC entrantes que reciba el usuario no se redirigirán a los extremos ubicados en sitios diferentes del de la puerta de enlace RTC, para evitar que se omitan los números de pago de RTC.

  - Cuando un usuario está ubicado en un sitio de red que la implementación de Lync Server desconoce, el enrutamiento de las llamadas salientes se realizará según la directiva de voz asignada al usuario, hacia las puertas de enlace RTC que no estén sujetas a restricciones del enrutamiento basado en ubicación. Las llamadas de RTC entrantes no se redirigirán a los extremos ubicados en sitios de red desconocidos, para evitar que se omitan los números de pago de RTC.

## Vea también

#### Otros recursos

[Instrucciones para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)

