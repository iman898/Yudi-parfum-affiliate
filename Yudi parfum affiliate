import { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Label } from "@/components/ui/label";
import { motion } from "framer-motion";
import { Tabs, TabsList, TabsTrigger, TabsContent } from "@/components/ui/tabs";

export default function AffiliateDashboard() {
  const [form, setForm] = useState({ name: "", email: "" });
  const [submitted, setSubmitted] = useState(false);
  const [points, setPoints] = useState(120); // Dummy point untuk contoh

  const handleChange = (e) => {
    setForm({ ...form, [e.target.name]: e.target.value });
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    setSubmitted(true);
    // Simpan ke database atau kirim ke backend
  };

  return (
    <div className="min-h-screen bg-gradient-to-br from-yellow-100 to-yellow-50 flex flex-col items-center justify-center px-4 py-10">
      <motion.h1
        initial={{ opacity: 0, y: -20 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.6 }}
        className="text-4xl font-bold text-yellow-800 mb-6"
      >
        Program Affiliate Yudi Parfum
      </motion.h1>

      <Tabs defaultValue={submitted ? "dashboard" : "daftar"} className="w-full max-w-xl">
        <TabsList className="grid grid-cols-2 bg-yellow-200 border border-yellow-400 rounded-xl mb-4">
          <TabsTrigger value="daftar" className="text-yellow-900 font-semibold">Daftar</TabsTrigger>
          <TabsTrigger value="dashboard" className="text-yellow-900 font-semibold">Dashboard</TabsTrigger>
        </TabsList>

        <TabsContent value="daftar">
          <Card className="bg-white border-4 border-yellow-300 shadow-2xl rounded-2xl">
            <CardContent className="p-6">
              {!submitted ? (
                <form onSubmit={handleSubmit} className="space-y-4">
                  <div>
                    <Label htmlFor="name" className="text-yellow-900 font-semibold">
                      Nama Lengkap
                    </Label>
                    <Input
                      id="name"
                      name="name"
                      type="text"
                      value={form.name}
                      onChange={handleChange}
                      required
                      className="mt-1 border-yellow-300"
                    />
                  </div>
                  <div>
                    <Label htmlFor="email" className="text-yellow-900 font-semibold">
                      Email
                    </Label>
                    <Input
                      id="email"
                      name="email"
                      type="email"
                      value={form.email}
                      onChange={handleChange}
                      required
                      className="mt-1 border-yellow-300"
                    />
                  </div>
                  <Button
                    type="submit"
                    className="w-full bg-yellow-500 text-white hover:bg-yellow-600 font-bold"
                  >
                    Daftar Sekarang
                  </Button>
                </form>
              ) : (
                <div className="text-center text-yellow-900">
                  <h2 className="text-xl font-semibold mb-2">Terima kasih telah mendaftar!</h2>
                  <p>Pendaftaran Anda telah kami terima. Silakan cek dashboard Anda.</p>
                </div>
              )}
            </CardContent>
          </Card>
        </TabsContent>

        <TabsContent value="dashboard">
          <Card className="bg-white border-4 border-yellow-300 shadow-2xl rounded-2xl">
            <CardContent className="p-6">
              <h2 className="text-2xl font-bold text-yellow-800 mb-4">Dashboard Reseller</h2>
              <div className="text-lg text-yellow-900 mb-2">Selamat datang, {form.name || "Reseller"}!</div>
              <div className="text-md text-yellow-800">Email: {form.email || "-"}</div>
              <div className="text-3xl font-bold text-yellow-600 mt-6">{points} Poin</div>
              <p className="text-yellow-700 mt-2">Gunakan poin Anda untuk mendapatkan reward menarik dari Yudi Parfum!</p>
            </CardContent>
          </Card>
        </TabsContent>
      </Tabs>
    </div>
  );
}
