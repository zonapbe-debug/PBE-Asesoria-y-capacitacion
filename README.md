import React, { useState } from 'react';
import { Button } from "/components/ui/button";
import { Card, CardContent, CardDescription, CardHeader, CardTitle } from "/components/ui/card";
import { Input } from "/components/ui/input";
import { Textarea } from "/components/ui/textarea";
import { Label } from "/components/ui/label";
import { Select, SelectContent, SelectItem, SelectTrigger, SelectValue } from "@/components/ui/select";
import { Menu, X, Mail, Calendar, Users, Check, Shield, Clock } from "lucide-react";

export default function PBEAsesoriaCapacitacion() {
  const [isMenuOpen, setIsMenuOpen] = useState(false);
  const [formData, setFormData] = useState({
    nombre: '',
    email: '',
    telefono: '',
    especialidad: '',
    tema: '',
    mensaje: ''
  });

  const handleInputChange = (field: string, value: string) => {
    setFormData(prev => ({ ...prev, [field]: value }));
  };

  const handleSubmit = (e: React.FormEvent) => {
    e.preventDefault();
    alert('Gracias por contactarnos. Nos pondremos en contacto contigo dentro de 24 horas.');
    setFormData({
      nombre: '',
      email: '',
      telefono: '',
      especialidad: '',
      tema: '',
      mensaje: ''
    });
  };

  const handleWhatsAppClick = () => {
    window.open('https://wa.me/message/C76TFVIPMRXXO1', '_blank');
  };

  return (
    <div className="min-h-screen bg-white">
      {/* Header */}
      <header className="bg-blue-900 text-white shadow-lg">
        <div className="container mx-auto px-4 py-4">
          <div className="flex items-center justify-between">
            <div className="flex items-center space-x-3">
              <img 
                src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/c47b73d0-fe17-4652-b193-2d237257b1ce.png" 
                alt="Logo de PBE Asesoría y Capacitación con balanza de justicia y libro académico" 
                className="w-12 h-12 rounded-full"
              />
              <div>
                <h1 className="text-2xl font-bold">PBE Asesoría y Capacitación</h1>
                <p className="text-blue-200 text-sm">Especialistas en Derecho y Desarrollo Académico</p>
              </div>
            </div>
            
            <div className="hidden lg:flex items-center space-x-4">
              <div className="text-right text-sm">
                <p className="text-blue-200">WhatsApp: 927 717 173</p>
                <p className="text-blue-200">zonapbe@gmail.com</p>
              </div>
              <Button 
                onClick={handleWhatsAppClick}
                className="bg-green-600 hover:bg-green-700 text-white px-4 py-2"
              >
                Contáctanos por WhatsApp
              </Button>
            </div>
            
            <nav className="hidden md:flex lg:hidden space-x-6">
              <a href="#inicio" className="hover:text-blue-200 transition-colors">Inicio</a>
              <a href="#servicios" className="hover:text-blue-200 transition-colors">Servicios</a>
              <a href="#especialidades" className="hover:text-blue-200 transition-colors">Especialidades</a>
              <a href="#proceso" className="hover:text-blue-200 transition-colors">Proceso</a>
              <a href="#contacto" className="hover:text-blue-200 transition-colors">Contacto</a>
            </nav>

            <Button
              variant="ghost"
              size="sm"
              className="md:hidden text-white hover:bg-blue-800"
              onClick={() => setIsMenuOpen(!isMenuOpen)}
            >
              {isMenuOpen ? <X size={24} /> : <Menu size={24} />}
            </Button>
          </div>

          {/* Navigation Menu for larger screens */}
          <nav className="hidden lg:flex justify-center space-x-8 mt-4">
            <a href="#inicio" className="hover:text-blue-200 transition-colors">Inicio</a>
            <a href="#servicios" className="hover:text-blue-200 transition-colors">Servicios</a>
            <a href="#especialidades" className="hover:text-blue-200 transition-colors">Especialidades</a>
            <a href="#proceso" className="hover:text-blue-200 transition-colors">Proceso</a>
            <a href="#contacto" className="hover:text-blue-200 transition-colors">Contacto</a>
          </nav>

          {/* Mobile Menu */}
          {isMenuOpen && (
            <nav className="md:hidden mt-4 pb-4 border-t border-blue-800 pt-4">
              <div className="flex flex-col space-y-2">
                <div className="mb-4 text-center">
                  <p className="text-blue-200 text-sm">WhatsApp: 927 717 173</p>
                  <p className="text-blue-200 text-sm">zonapbe@gmail.com</p>
                  <Button 
                    onClick={handleWhatsAppClick}
                    className="bg-green-600 hover:bg-green-700 text-white mt-2 w-full"
                  >
                    Contáctanos por WhatsApp
                  </Button>
                </div>
                <a href="#inicio" className="hover:text-blue-200 transition-colors py-2">Inicio</a>
                <a href="#servicios" className="hover:text-blue-200 transition-colors py-2">Servicios</a>
                <a href="#especialidades" className="hover:text-blue-200 transition-colors py-2">Especialidades</a>
                <a href="#proceso" className="hover:text-blue-200 transition-colors py-2">Proceso</a>
                <a href="#contacto" className="hover:text-blue-200 transition-colors py-2">Contacto</a>
              </div>
            </nav>
          )}
        </div>
      </header>

      {/* WhatsApp Floating Button */}
      <div className="fixed bottom-6 right-6 z-50">
        <Button
          onClick={handleWhatsAppClick}
          className="bg-green-500 hover:bg-green-600 text-white p-4 rounded-full shadow-lg animate-pulse"
          size="lg"
        >
          <img 
            src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/9f844301-d05e-4206-a388-6084a587d5d0.png" 
            alt="Icono de WhatsApp para chat directo" 
            className="w-6 h-6"
          />
        </Button>
      </div>

      {/* Hero Section */}
      <section id="inicio" className="bg-gradient-to-br from-blue-50 to-white py-16">
        <div className="container mx-auto px-4">
          <div className="grid md:grid-cols-2 gap-12 items-center">
            <div>
              <h2 className="text-4xl md:text-5xl font-bold text-blue-900 mb-6">
                Asesoría Profesional para tu <span className="text-red-600">Tesis de Derecho</span>
              </h2>
              <p className="text-xl text-gray-700 mb-8">
                En PBE Asesoría y Capacitación somos especialistas en asesoramiento académico jurídico 
                para estudiantes peruanos. Te acompañamos desde la idea inicial hasta la sustentación exitosa.
              </p>
              <div className="flex flex-col sm:flex-row gap-4">
                <Button 
                  size="lg" 
                  className="bg-blue-900 hover:bg-blue-800"
                  onClick={() => document.getElementById('contacto')?.scrollIntoView({ behavior: 'smooth' })}
                >
                  Solicitar Asesoría Gratuita
                </Button>
                <Button 
                  onClick={handleWhatsAppClick}
                  size="lg" 
                  className="bg-green-600 hover:bg-green-700"
                >
                  WhatsApp: 927 717 173
                </Button>
              </div>
            </div>
            <div className="relative">
              <img 
                src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/921683a8-7e6c-4dd8-98e5-9d9c8ff51e25.png" 
                alt="Estudiante de derecho peruano trabajando en su tesis con libros jurídicos y códigos legales del Perú en un escritorio profesional" 
                className="rounded-lg shadow-xl"
              />
              <div className="absolute -bottom-6 -left-6 bg-red-600 text-white p-4 rounded-lg shadow-lg">
                <p className="font-bold text-2xl">95%</p>
                <p className="text-sm">Tesis Aprobadas</p>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Services Section */}
      <section id="servicios" className="py-16 bg-white">
        <div className="container mx-auto px-4">
          <div className="text-center mb-12">
            <h2 className="text-3xl md:text-4xl font-bold text-blue-900 mb-4">
              Nuestros Servicios de Asesoría y Capacitación
            </h2>
            <p className="text-xl text-gray-600 max-w-3xl mx-auto">
              Ofrecemos servicios integrales para el desarrollo de tu tesis de derecho, 
              adaptados a las exigencias académicas peruanas con PBE Asesoría y Capacitación.
            </p>
          </div>

          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
            <Card className="hover:shadow-lg transition-shadow border-l-4 border-l-blue-900">
              <CardHeader>
                <div className="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center mb-4">
                  <img 
                    src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/e11b6205-5b45-469c-907e-d3ddacd2866a.png" 
                    alt="Icono de planificación de tesis con cronograma y estructura académica" 
                    className="w-8 h-8"
                  />
                </div>
                <CardTitle className="text-blue-900">Planificación de Tesis</CardTitle>
                <CardDescription>
                  Definición del tema, problema de investigación y estructura metodológica
                </CardDescription>
              </CardHeader>
              <CardContent>
                <ul className="space-y-2 text-sm text-gray-600">
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Selección de tema jurídico relevante
                  </li>
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Formulación de problema legal
                  </li>
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Diseño metodológico
                  </li>
                </ul>
              </CardContent>
            </Card>

            <Card className="hover:shadow-lg transition-shadow border-l-4 border-l-red-600">
              <CardHeader>
                <div className="w-12 h-12 bg-red-100 rounded-lg flex items-center justify-center mb-4">
                  <img 
                    src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/b44fad94-0006-4296-aaff-866e33650409.png" 
                    alt="Icono de investigación jurídica con lupa examinando documentos legales peruanos" 
                    className="w-8 h-8"
                  />
                </div>
                <CardTitle className="text-blue-900">Investigación Jurídica</CardTitle>
                <CardDescription>
                  Marco teórico, jurisprudencia y análisis de legislación peruana
                </CardDescription>
              </CardHeader>
              <CardContent>
                <ul className="space-y-2 text-sm text-gray-600">
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Revisión jurisprudencial TC y PJ
                  </li>
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Análisis normativo vigente
                  </li>
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Doctrina jurídica nacional
                  </li>
                </ul>
              </CardContent>
            </Card>

            <Card className="hover:shadow-lg transition-shadow border-l-4 border-l-green-600">
              <CardHeader>
                <div className="w-12 h-12 bg-green-100 rounded-lg flex items-center justify-center mb-4">
                  <img 
                    src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/205d95ea-7b5f-45a4-b1d9-329c6f3752bc.png" 
                    alt="Icono de redacción académica con pluma escribiendo en documento legal formal" 
                    className="w-8 h-8"
                  />
                </div>
                <CardTitle className="text-blue-900">Redacción Académica</CardTitle>
                <CardDescription>
                  Desarrollo de capítulos con estilo académico y normas APA
                </CardDescription>
              </CardHeader>
              <CardContent>
                <ul className="space-y-2 text-sm text-gray-600">
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Redacción técnica jurídica
                  </li>
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Formato académico APA
                  </li>
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Revisión y corrección
                  </li>
                </ul>
              </CardContent>
            </Card>

            <Card className="hover:shadow-lg transition-shadow border-l-4 border-l-yellow-600">
              <CardHeader>
                <div className="w-12 h-12 bg-yellow-100 rounded-lg flex items-center justify-center mb-4">
                  <img 
                    src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/86c5e6f8-8171-43a9-9522-ac6041f5808d.png" 
                    alt="Icono de asesoría metodológica con gráficos de investigación cualitativa y cuantitativa" 
                    className="w-8 h-8"
                  />
                </div>
                <CardTitle className="text-blue-900">Asesoría Metodológica</CardTitle>
                <CardDescription>
                  Diseño de instrumentos y análisis de resultados jurídicos
                </CardDescription>
              </CardHeader>
              <CardContent>
                <ul className="space-y-2 text-sm text-gray-600">
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Metodología cualitativa
                  </li>
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Análisis documental
                  </li>
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Entrevistas a expertos
                  </li>
                </ul>
              </CardContent>
            </Card>

            <Card className="hover:shadow-lg transition-shadow border-l-4 border-l-purple-600">
              <CardHeader>
                <div className="w-12 h-12 bg-purple-100 rounded-lg flex items-center justify-center mb-4">
                  <img 
                    src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/0839153d-389c-48ed-9e05-1cadadee5105.png" 
                    alt="Icono de sustentación de tesis con podio de presentación y jurado académico" 
                    className="w-8 h-8"
                  />
                </div>
                <CardTitle className="text-blue-900">Preparación para Sustentación</CardTitle>
                <CardDescription>
                  Entrenamiento para defensa oral y manejo de preguntas del jurado
                </CardDescription>
              </CardHeader>
              <CardContent>
                <ul className="space-y-2 text-sm text-gray-600">
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Simulacros de sustentación
                  </li>
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Preparación de diapositivas
                  </li>
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Técnicas de exposición
                  </li>
                </ul>
              </CardContent>
            </Card>

            <Card className="hover:shadow-lg transition-shadow border-l-4 border-l-indigo-600">
              <CardHeader>
                <div className="w-12 h-12 bg-indigo-100 rounded-lg flex items-center justify-center mb-4">
                  <img 
                    src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/d1318f92-e9c2-43c5-96ec-556d6c3a1889.png" 
                    alt="Icono de revisión antiplagio con escudo de verificación y documento aprobado" 
                    className="w-8 h-8"
                  />
                </div>
                <CardTitle className="text-blue-900">Control de Originalidad</CardTitle>
                <CardDescription>
                  Verificación antiplagio y garantía de originalidad académica
                </CardDescription>
              </CardHeader>
              <CardContent>
                <ul className="space-y-2 text-sm text-gray-600">
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Análisis Turnitin
                  </li>
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Reporte de originalidad
                  </li>
                  <li className="flex items-center gap-2">
                    <Check size={16} className="text-green-600" />
                    Certificado de autenticidad
                  </li>
                </ul>
              </CardContent>
            </Card>
          </div>
        </div>
      </section>

      {/* Legal Specialties Section */}
      <section id="especialidades" className="py-16 bg-gray-50">
        <div className="container mx-auto px-4">
          <div className="text-center mb-12">
            <h2 className="text-3xl md:text-4xl font-bold text-blue-900 mb-4">
              Especialidades Jurídicas
            </h2>
            <p className="text-xl text-gray-600 max-w-3xl mx-auto">
              En PBE Asesoría y Capacitación contamos con asesores especializados en todas las ramas del derecho peruano
            </p>
          </div>

          <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
            <div className="bg-white p-6 rounded-lg shadow hover:shadow-md transition-shadow text-center">
              <img 
                src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/6e7c82f5-8320-49dd-bd42-bdc7e6db3e3e.png" 
                alt="Símbolo de derecho civil peruano con código civil y contratos familiares" 
                className="w-16 h-16 mx-auto mb-4 rounded-full"
              />
              <h3 className="font-bold text-blue-900 mb-2">Derecho Civil</h3>
              <p className="text-sm text-gray-600">Contratos, familia, sucesiones, responsabilidad civil</p>
            </div>

            <div className="bg-white p-6 rounded-lg shadow hover:shadow-md transition-shadow text-center">
              <img 
                src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/5ea47e64-c945-4e2a-9a48-dfde68414eb2.png" 
                alt="Símbolo de derecho penal peruano con código penal y sistema de justicia criminal" 
                className="w-16 h-16 mx-auto mb-4 rounded-full"
              />
              <h3 className="font-bold text-blue-900 mb-2">Derecho Penal</h3>
              <p className="text-sm text-gray-600">Derecho penal, procesal penal, criminología</p>
            </div>

            <div className="bg-white p-6 rounded-lg shadow hover:shadow-md transition-shadow text-center">
              <img 
                src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/75c60fbf-cde1-4c4d-977b-5461d4d7628d.png" 
                alt="Símbolo de derecho constitucional peruano con constitución política del Perú y derechos fundamentales" 
                className="w-16 h-16 mx-auto mb-4 rounded-full"
              />
              <h3 className="font-bold text-blue-900 mb-2">Derecho Constitucional</h3>
              <p className="text-sm text-gray-600">Derechos fundamentales, amparo, hábeas corpus</p>
            </div>

            <div className="bg-white p-6 rounded-lg shadow hover:shadow-md transition-shadow text-center">
              <img 
                src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/cead3e5b-f4b1-44d2-ad4f-b88d8da60e27.png" 
                alt="Símbolo de derecho administrativo peruano con entidades públicas y procedimientos administrativos" 
                className="w-16 h-16 mx-auto mb-4 rounded-full"
              />
              <h3 className="font-bold text-blue-900 mb-2">Derecho Administrativo</h3>
              <p className="text-sm text-gray-600">Procedimiento administrativo, contrataciones del Estado</p>
            </div>

            <div className="bg-white p-6 rounded-lg shadow hover:shadow-md transition-shadow text-center">
              <img 
                src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/4363f518-ac04-4eca-a6e5-afc48e8f7fa7.png" 
                alt="Símbolo de derecho laboral peruano con relaciones de trabajo y legislación laboral vigente" 
                className="w-16 h-16 mx-auto mb-4 rounded-full"
              />
              <h3 className="font-bold text-blue-900 mb-2">Derecho Laboral</h3>
              <p className="text-sm text-gray-600">Relaciones laborales, seguridad social, despidos</p>
            </div>

            <div className="bg-white p-6 rounded-lg shadow hover:shadow-md transition-shadow text-center">
              <img 
                src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/57778f58-8ac4-4e4d-b5c7-abcafad08f2f.png" 
                alt="Símbolo de derecho comercial peruano con empresas mercantiles y código de comercio" 
                className="w-16 h-16 mx-auto mb-4 rounded-full"
              />
              <h3 className="font-bold text-blue-900 mb-2">Derecho Empresarial</h3>
              <p className="text-sm text-gray-600">Sociedades, derecho mercantil, concursal</p>
            </div>

            <div className="bg-white p-6 rounded-lg shadow hover:shadow-md transition-shadow text-center">
              <img 
                src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/9eed7601-2744-4b90-b8dd-1993368137e5.png" 
                alt="Símbolo de derecho tributario peruano con SUNAT y código tributario nacional" 
                className="w-16 h-16 mx-auto mb-4 rounded-full"
              />
              <h3 className="font-bold text-blue-900 mb-2">Derecho Tributario</h3>
              <p className="text-sm text-gray-600">Código tributario, procedimientos SUNAT</p>
            </div>

            <div className="bg-white p-6 rounded-lg shadow hover:shadow-md transition-shadow text-center">
              <img 
                src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/2d5e225f-be8f-4816-aad3-31739021289f.png" 
                alt="Símbolo de derecho internacional peruano con tratados internacionales y derecho comparado" 
                className="w-16 h-16 mx-auto mb-4 rounded-full"
              />
              <h3 className="font-bold text-blue-900 mb-2">Derecho Internacional</h3>
              <p className="text-sm text-gray-600">Derecho internacional público y privado</p>
            </div>
          </div>
        </div>
      </section>

      {/* Process Section */}
      <section id="proceso" className="py-16 bg-white">
        <div className="container mx-auto px-4">
          <div className="text-center mb-12">
            <h2 className="text-3xl md:text-4xl font-bold text-blue-900 mb-4">
              Nuestro Proceso de Asesoría en PBE
            </h2>
            <p className="text-xl text-gray-600 max-w-3xl mx-auto">
              Un proceso estructurado y probado que garantiza el éxito de tu tesis
            </p>
          </div>

          <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
            <div className="text-center">
              <div className="w-20 h-20 bg-blue-900 text-white rounded-full flex items-center justify-center text-2xl font-bold mx-auto mb-4">
                1
              </div>
              <h3 className="text-xl font-bold text-blue-900 mb-3">Consulta Inicial</h3>
              <p className="text-gray-600">
                Evaluamos tu perfil académico y definimos objetivos específicos para tu tesis jurídica
              </p>
            </div>

            <div className="text-center">
              <div className="w-20 h-20 bg-red-600 text-white rounded-full flex items-center justify-center text-2xl font-bold mx-auto mb-4">
                2
              </div>
              <h3 className="text-xl font-bold text-blue-900 mb-3">Plan Personalizado</h3>
              <p className="text-gray-600">
                Diseñamos un plan de trabajo adaptado a tu especialidad y cronograma universitario
              </p>
            </div>

            <div className="text-center">
              <div className="w-20 h-20 bg-green-600 text-white rounded-full flex items-center justify-center text-2xl font-bold mx-auto mb-4">
                3
              </div>
              <h3 className="text-xl font-bold text-blue-900 mb-3">Desarrollo Guiado</h3>
              <p className="text-gray-600">
                Te acompañamos paso a paso en la investigación y redacción de cada capítulo
              </p>
            </div>

            <div className="text-center">
              <div className="w-20 h-20 bg-purple-600 text-white rounded-full flex items-center justify-center text-2xl font-bold mx-auto mb-4">
                4
              </div>
              <h3 className="text-xl font-bold text-blue-900 mb-3">Sustentación Exitosa</h3>
              <p className="text-gray-600">
                Preparamos tu defensa oral con simulacros hasta lograr una presentación impecable
              </p>
            </div>
          </div>
        </div>
      </section>

      {/* Stats Section */}
      <section className="py-16 bg-gray-50">
        <div className="container mx-auto px-4">
          <div className="grid md:grid-cols-4 gap-8 text-center">
            <div>
              <div className="text-4xl font-bold text-blue-900 mb-2">500+</div>
              <p className="text-gray-600">Tesis Asesoradas</p>
            </div>
            <div>
              <div className="text-4xl font-bold text-red-600 mb-2">95%</div>
              <p className="text-gray-600">Tasa de Aprobación</p>
            </div>
            <div>
              <div className="text-4xl font-bold text-green-600 mb-2">8</div>
              <p className="text-gray-600">Años de Experiencia</p>
            </div>
            <div>
              <div className="text-4xl font-bold text-purple-600 mb-2">50+</div>
              <p className="text-gray-600">Universidades Atendidas</p>
            </div>
          </div>
        </div>
      </section>

      {/* Contact Form Section */}
      <section id="contacto" className="py-16 bg-white">
        <div className="container mx-auto px-4">
          <div className="grid md:grid-cols-2 gap-12">
            <div>
              <h2 className="text-3xl md:text-4xl font-bold text-blue-900 mb-6">
                Solicita tu Asesoría Gratuita en PBE
              </h2>
              <p className="text-xl text-gray-600 mb-8">
                Completa el formulario y nos pondremos en contacto contigo en menos de 24 horas 
                para evaluar tu proyecto de tesis con nuestros especialistas de PBE Asesoría y Capacitación.
              </p>

              <div className="space-y-4">
                <div className="flex items-center gap-3">
                  <div className="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center">
                    <Clock className="w-6 h-6 text-blue-900" />
                  </div>
                  <div>
                    <h4 className="font-bold text-blue-900">Respuesta Rápida</h4>
                    <p className="text-gray-600">Te contactamos en máximo 24 horas</p>
                  </div>
                </div>

                <div className="flex items-center gap-3">
                  <div className="w-12 h-12 bg-red-100 rounded-lg flex items-center justify-center">
                    <Shield className="w-6 h-6 text-red-600" />
                  </div>
                  <div>
                    <h4 className="font-bold text-blue-900">Confidencialidad Total</h4>
                    <p className="text-gray-600">Tu información está completamente protegida</p>
                  </div>
                </div>

                <div className="flex items-center gap-3">
                  <div className="w-12 h-12 bg-green-100 rounded-lg flex items-center justify-center">
                    <Users className="w-6 h-6 text-green-600" />
                  </div>
                  <div>
                    <h4 className="font-bold text-blue-900">Asesores Especializados</h4>
                    <p className="text-gray-600">Abogados con experiencia académica</p>
                  </div>
                </div>

                <div className="bg-green-50 p-4 rounded-lg mt-6">
                  <h4 className="font-bold text-green-800 mb-2">Contáctanos Directamente:</h4>
                  <div className="space-y-2">
                    <p className="text-green-700">📱 WhatsApp: <span className="font-semibold">927 717 173</span></p>
                    <p className="text-green-700">✉️ Email: <span className="font-semibold">zonapbe@gmail.com</span></p>
                  </div>
                  <Button 
                    onClick={handleWhatsAppClick}
                    className="bg-green-600 hover:bg-green-700 text-white mt-3 w-full"
                  >
                    Escribir por WhatsApp Ahora
                  </Button>
                </div>
              </div>
            </div>

            <div>
              <Card className="shadow-lg">
                <CardHeader>
                  <CardTitle className="text-blue-900">Formulario de Contacto - PBE</CardTitle>
                  <CardDescription>
                    Todos los campos marcados con * son obligatorios
                  </CardDescription>
                </CardHeader>
                <CardContent>
                  <form onSubmit={handleSubmit} className="space-y-4">
                    <div>
                      <Label htmlFor="nombre">Nombre Completo *</Label>
                      <Input
                        id="nombre"
                        value={formData.nombre}
                        onChange={(e) => handleInputChange('nombre', e.target.value)}
                        placeholder="Tu nombre completo"
                        required
                      />
                    </div>

                    <div>
                      <Label htmlFor="email">Correo Electrónico *</Label>
                      <Input
                        id="email"
                        type="email"
                        value={formData.email}
                        onChange={(e) => handleInputChange('email', e.target.value)}
                        placeholder="tu@email.com"
                        required
                      />
                    </div>

                    <div>
                      <Label htmlFor="telefono">Teléfono *</Label>
                      <Input
                        id="telefono"
                        value={formData.telefono}
                        onChange={(e) => handleInputChange('telefono', e.target.value)}
                        placeholder="999 999 999"
                        required
                      />
                    </div>

                    <div>
                      <Label htmlFor="especialidad">Especialidad Jurídica *</Label>
                      <Select onValueChange={(value) => handleInputChange('especialidad', value)}>
                        <SelectTrigger>
                          <SelectValue placeholder="Selecciona tu especialidad" />
                        </SelectTrigger>
                        <SelectContent>
                          <SelectItem value="civil">Derecho Civil</SelectItem>
                          <SelectItem value="penal">Derecho Penal</SelectItem>
                          <SelectItem value="constitucional">Derecho Constitucional</SelectItem>
                          <SelectItem value="administrativo">Derecho Administrativo</SelectItem>
                          <SelectItem value="laboral">Derecho Laboral</SelectItem>
                          <SelectItem value="empresarial">Derecho Empresarial</SelectItem>
                          <SelectItem value="tributario">Derecho Tributario</SelectItem>
                          <SelectItem value="internacional">Derecho Internacional</SelectItem>
                          <SelectItem value="otro">Otra especialidad</SelectItem>
                        </SelectContent>
                      </Select>
                    </div>

                    <div>
                      <Label htmlFor="tema">Tema de Tesis (Opcional)</Label>
                      <Input
                        id="tema"
                        value={formData.tema}
                        onChange={(e) => handleInputChange('tema', e.target.value)}
                        placeholder="Breve descripción de tu tema"
                      />
                    </div>

                    <div>
                      <Label htmlFor="mensaje">Mensaje Adicional</Label>
                      <Textarea
                        id="mensaje"
                        value={formData.mensaje}
                        onChange={(e) => handleInputChange('mensaje', e.target.value)}
                        placeholder="Cuéntanos más sobre tu proyecto o consultas específicas"
                        rows={4}
                      />
                    </div>

                    <Button type="submit" className="w-full bg-blue-900 hover:bg-blue-800">
                      <Mail className="w-4 h-4 mr-2" />
                      Solicitar Asesoría Gratuita
                    </Button>

                    <p className="text-sm text-gray-600 text-center">
                      Al enviar este formulario aceptas nuestros términos de servicio y política de privacidad
                    </p>
                  </form>
                </CardContent>
              </Card>
            </div>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-blue-900 text-white py-12">
        <div className="container mx-auto px-4">
          <div className="grid md:grid-cols-4 gap-8">
            <div>
              <div className="flex items-center gap-3 mb-4">
                <img 
                  src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/95866985-7017-4712-a608-e1e19bb80cc7.png" 
                  alt="Logo footer de PBE Asesoría y Capacitación con balanza de justicia" 
                  className="w-10 h-10 rounded-full"
                />
                <h3 className="text-xl font-bold">PBE Asesoría y Capacitación</h3>
              </div>
              <p className="text-blue-200 mb-4">
                Líderes en asesoría académica jurídica para estudiantes peruanos desde 2016.
              </p>
              <div className="flex space-x-3">
                <img 
                  src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/e432927c-2f50-45b3-95cf-ba965ef1c763.png" 
                  alt="Icono de Facebook para seguir noticias jurídicas y contenido académico" 
                  className="w-8 h-8 rounded hover:opacity-80 cursor-pointer"
                />
                <img 
                  src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/aca3c6ec-ef1e-41df-92d5-311e34b36ff8.png" 
                  alt="Icono de LinkedIn para conexiones profesionales del ámbito jurídico peruano" 
                  className="w-8 h-8 rounded hover:opacity-80 cursor-pointer"
                />
                <Button
                  onClick={handleWhatsAppClick}
                  variant="ghost"
                  size="sm"
                  className="p-0 h-8 w-8"
                >
                  <img 
                    src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/6c5ede33-ac3d-4fd1-9a94-97ed7eb7a6d4.png" 
                    alt="Icono de WhatsApp para comunicación directa con asesores de tesis" 
                    className="w-8 h-8 rounded hover:opacity-80"
                  />
                </Button>
              </div>
            </div>

            <div>
              <h4 className="font-bold mb-4">Servicios</h4>
              <ul className="space-y-2 text-blue-200">
                <li><a href="#" className="hover:text-white">Planificación de Tesis</a></li>
                <li><a href="#" className="hover:text-white">Investigación Jurídica</a></li>
                <li><a href="#" className="hover:text-white">Redacción Académica</a></li>
                <li><a href="#" className="hover:text-white">Asesoría Metodológica</a></li>
                <li><a href="#" className="hover:text-white">Preparación Sustentación</a></li>
              </ul>
            </div>

            <div>
              <h4 className="font-bold mb-4">Especialidades</h4>
              <ul className="space-y-2 text-blue-200">
                <li><a href="#" className="hover:text-white">Derecho Civil</a></li>
                <li><a href="#" className="hover:text-white">Derecho Penal</a></li>
                <li><a href="#" className="hover:text-white">Derecho Constitucional</a></li>
                <li><a href="#" className="hover:text-white">Derecho Laboral</a></li>
                <li><a href="#" className="hover:text-white">Derecho Empresarial</a></li>
              </ul>
            </div>

            <div>
              <h4 className="font-bold mb-4">Contacto</h4>
              <div className="space-y-3 text-blue-200">
                <div className="flex items-center gap-2">
                  <Mail className="w-4 h-4" />
                  <span>zonapbe@gmail.com</span>
                </div>
                <div className="flex items-center gap-2">
                  <Calendar className="w-4 h-4" />
                  <span>WhatsApp: 927 717 173</span>
                </div>
                <div className="flex items-center gap-2">
                  <Clock className="w-4 h-4" />
                  <span>Lun - Sáb: 8:00 - 20:00</span>
                </div>
                <Button 
                  onClick={handleWhatsAppClick}
                  className="bg-green-600 hover:bg-green-700 text-white mt-2"
                >
                  Contactar por WhatsApp
                </Button>
              </div>
            </div>
          </div>

          <div className="border-t border-blue-800 mt-8 pt-8 text-center text-blue-200">
            <p>© 2024 PBE Asesoría y Capacitación. Todos los derechos reservados.</p>
            <p className="mt-2">RUC: 20123456789 - Lima, Perú</p>
          </div>
        </div>
      </footer>
    </div>
  );
}
