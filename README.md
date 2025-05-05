


# 🗺️ Reverse Geocoding - Zona Metropolitana de Guadalajara

Este proyecto levanta una instancia de Nominatim utilizando datos de OpenStreetMap enfocados en la **Zona Metropolitana de Guadalajara**, permitiendo realizar geocodificación inversa desde coordenadas a direcciones.

## 📦 Descripción

Utiliza la imagen oficial `mediagis/nominatim:5.1` con un archivo `.osm.pbf` local recortado para Guadalajara. Ideal para proyectos de smart cities, análisis urbano o sistemas de movilidad en la región.

## ⚙️ Requisitos

### Hardware mínimo (para desarrollo o pruebas locales)

| Recurso        | Valor             |
|----------------|-------------------|
| RAM            | 4 GB              |
| CPU            | 2 vCPU            |
| Disco SSD      | 10 GB             |
| Swap           | 2–4 GB (opcional) |

### Hardware recomendado (para producción ligera)

| Recurso        | Valor             |
|----------------|-------------------|
| RAM            | 8 GB              |
| CPU            | 4 vCPU            |
| Disco SSD      | 20–25 GB          |
| Swap           | 4 GB              |

## 🧱 Espacio en disco

- `.osm.pbf` recortado para Guadalajara: ~80 MB
- Base de datos importada: ~1.5 GB
- Espacio total requerido: ~4 GB

## 🚀 Cómo levantar el proyecto

### 1. Requisitos previos

- Tener instalado `Docker` y `docker-compose`
- El archivo `guadalajara.osm.pbf` debe estar en la carpeta `./data`

### 2. Levantar los servicios

```bash
docker compose up --build
```

Esto descargará la imagen de Nominatim, importará los datos y levantará el servidor en `http://localhost:8080`.

## 🔍 Cómo probarlo

Puedes probarlo usando `curl` con coordenadas del centro de Guadalajara:

```bash
curl "http://localhost:8080/reverse?lat=20.6736&lon=-103.344&format=json"
```

Esto te devolverá un JSON con la dirección correspondiente a esas coordenadas. Ideal para integrarlo en otros sistemas. 🌐