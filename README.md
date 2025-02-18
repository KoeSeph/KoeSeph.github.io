
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CRM Form</title>
    <script src="https://unpkg.com/react@18/umd/react.production.min.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js" crossorigin></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css">
</head>
<body class="bg-gray-100 flex justify-center items-center h-screen">
    <div id="root"></div>

    <script type="text/babel">
        function CRMForm() {
            const [formData, setFormData] = React.useState({
                name: "",
                email: "",
                phone: "",
                classInterest: "",
                language: "English",
            });

            const [showPopup, setShowPopup] = React.useState(false); // Success popup

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

                // Convert form data into Google Form format
                const formUrl = "https://docs.google.com/forms/u/0/d/e/1FAIpQLSdV11p4oXCH5JhN3iF1aQz1kTGrzoYB_q1oeBUVEZ6SqYOLLw/formResponse";
                const formDataToSend = new FormData();
                formDataToSend.append("entry.727987131", formData.name);
                formDataToSend.append("entry.1934937746", formData.email);
                formDataToSend.append("entry.1820786173", formData.phone);
                formDataToSend.append("entry.498337758", formData.classInterest);
                

                try {
                    await fetch(formUrl, {
                        method: "POST",
                        body: formDataToSend,
                        mode: "no-cors", // Bypasses CORS issues
                    });

                    setShowPopup(true); // Show success message
                    setTimeout(() => setShowPopup(false), 3000); // Hide after 3 sec

                    setFormData({ name: "", email: "", phone: "", classInterest: "", language: formData.language });

                } catch (error) {
                    console.error("Error submitting form:", error);
                    alert(formData.language === "English" ? "Submission failed!" : "¡Error al enviar!");
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

                    {showPopup && (
                        <div className="absolute top-10 right-10 p-4 bg-green-500 text-white rounded shadow-md">
                            {formData.language === "English" ? "Thank you! Your form has been submitted." : "¡Gracias! Su formulario ha sido enviado."}
                        </div>
                    )}
                </div>
            );
        }

        ReactDOM.render(<CRMForm />, document.getElementById("root"));
    </script>
</body>
</html>
