import React, { useState } from "react";

export default function CRMForm() {
  const [formData, setFormData] = useState({
    name: "",
    email: "",
    phone: "",
    classInterest: "",
    language: "English",
  });

  const toggleLanguage = () => {
    setFormData((prev) => ({
      ...prev,
      language: prev.language === "English" ? "Spanish" : "English",
    }));
  };

  const handleChange = (e) => {
    setFormData({ ...formData, [e.target.name]: e.target.value });
  };

  const handleSubmit = async (e) => {
    e.preventDefault();
    const response = await fetch(
      "https://script.google.com/macros/s/AKfycbx0Ja5BTTi-8lMW3TMr-y-VpagDi0GZCvLZByGi9LeEPUprVilEY8AFI-eOeg7y7teGJQ/exec",
      {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify(formData),
      }
    );
    if (response.ok) {
      alert("Form submitted successfully!");
      setFormData({ name: "", email: "", phone: "", classInterest: "", language: formData.language });
    } else {
      alert("Failed to submit form. Please try again.");
    }
  };

  return (
    <div className="p-6 max-w-md mx-auto bg-white rounded-xl shadow-md space-y-4">
      <h2 className="text-xl font-bold">{formData.language === "English" ? "Class Registration" : "Registro de Clases"}</h2>
      <form onSubmit={handleSubmit} className="space-y-3">
        <input type="text" name="name" value={formData.name} onChange={handleChange} placeholder={formData.language === "English" ? "Name" : "Nombre"} className="w-full p-2 border rounded" required />
        <input type="email" name="email" value={formData.email} onChange={handleChange} placeholder="Email" className="w-full p-2 border rounded" required />
        <input type="tel" name="phone" value={formData.phone} onChange={handleChange} placeholder={formData.language === "English" ? "Phone Number" : "Número de Teléfono"} className="w-full p-2 border rounded" required />
        <input type="text" name="classInterest" value={formData.classInterest} onChange={handleChange} placeholder={formData.language === "English" ? "Class Interest" : "Interés en Clases"} className="w-full p-2 border rounded" required />
        <button type="submit" className="w-full p-2 bg-blue-500 text-white rounded">{formData.language === "English" ? "Submit" : "Enviar"}</button>
      </form>
      <button onClick={toggleLanguage} className="w-full p-2 mt-2 bg-gray-300 rounded">{formData.language === "English" ? "Switch to Spanish" : "Cambiar a Inglés"}</button>
    </div>
  );
}
