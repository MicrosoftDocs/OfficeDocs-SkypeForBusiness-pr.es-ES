---
title: Distribución de carga de conferencias
TOCTitle: Distribución de carga de conferencias
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48275333
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Distribución de carga de conferencias

 

_**Última modificación del tema:** 2012-10-22_

A diferencia de algunas otras soluciones dedicadas la videoconferencia, la arquitectura de Lync Server es un modelo de hardware compartidos. Esto significa que el mismo hardware es compartido por muchos de los componentes de software, cada uno de los cuales admite diferentes comunicaciones en tiempo real. Cada tipo de comunicaciones en tiempo real coloca cargas específicas en los servidores. Por ejemplo, el Servidor front-end puede ejecutar los componentes de enrutamiento del protocolo de inicio de sesión (SIP), las aplicaciones web (como la búsqueda de la libreta de direcciones), las aplicaciones de Servicio de conferencia web, Servicio de conferencia A/V, Telefonía IP empresarial (por ejemplo, Aplicación Operador de conferencia y Aplicación de grupo de respuesta), y Servidor de mediación. Un conjunto de bases de datos en el Servidor front-end también permiten el almacenamiento y procesamiento por parte de usuario, contacto, presencia, conferencias y datos de enrutamiento de voz. Con este intercambio de hardware, componentes, servicios y procesos compiten por recursos de CPU y memoria, por eso las cargas de trabajo de comunicación no tienen un impacto directo a escala del servidor.

En comparación con otras soluciones de videoconferencia basadas en el puerto de hardware, la arquitectura de las conferencias de Lync Server es un modelo sin reservas. Cuando un usuario programa una reunión, Lync Server crea un registro en la base de conferencias, que almacena los datos de la conferencia, pero no reserva ningún recurso de hardware para la reunión programada antes de tiempo. En cambio, Lync Server tiene lógica de equilibrio de carga incorporada para asignar dinámicamente recursos de conferencias en los Servidores front-end de manera que distribuye las cargas equitativamente en todos los Servidores front-end del grupo. Esto suministra y usa los recursos de hardware de forma eficaz, pero hace que sea difícil mantener reuniones muy grandes (especialmente sin una planificación adecuada). Por ejemplo, cuando un grupo de Lync Server 2013 se ejecuta cerca de su capacidad máxima, cada Servidor front-end puede alojar reuniones de aproximadamente 125 personas de tamaño medio. Agregar otra reunión pequeña no sería un problema, pero agregar una reunión de 1.000 usuarios sería un problema porque el Servidores front-end probablemente podría admitir esa reunión al mismo tiempo que las otras reuniones de 125 usuarios.

