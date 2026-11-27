class FunkcjaKwadratowa:
	def __init__(self, a, b, c):
		if type(a) != float and type(a) != int:
			raise TypeError('Oczekiwano liczby jako współczynnika przy x^2')
		if type(b) != float and type(b) != int:
			raise TypeError('Oczekiwano liczby jako współczynnika przy x')
		if type(c) != float and type(c) != int:
			raise TypeError('Oczekiwano liczby jako wyrazu wolnego')
		if a == 0:
			raise ValueError('Oczekiwano niezerowego współczynnika przy x^2')
		self.a = a
		self.b = b
		self.c = c
	def rozwiaz(self):
		sqrt_wyznacznik = self.wyznacznik() ** 0.5
		dwa_a = 2 * self.a
		return {(sqrt_wyznacznik - self.b) / dwa_a, -(sqrt_wyznacznik + self.b) / dwa_a}
	def wyznacznik(self):
		return self.b * self.b - 4 * self.a * self.c
	def czy_rosnaca(self, x):
		x_wierzch = self.os_symetrii()
		return (
			x != x_wierzch
			and (x < x_wierzch) != self.czy_wypukla()
		)
	def czy_wypukla(self):
		return self.a > 0
	def wierzcholek(self):
		return (self.os_symetrii(), self.ekstremum())
	def suma_rozwiazan(self):
		return -self.b / self.a
	def os_symetrii(self):
		return self.suma_rozwiazan() / 2
	def iloczyn_rozwiazan(self):
		return self.c / self.a
	def ekstremum(self):
		return self(self.os_symetrii())
	def pochodna(self):
		return lambda x: self.a * 2 * x + self.b
	def pierwotna(self):
		return lambda x: ((self.a / 3 * x + self.b / 2) * x + self.c) * x
	def __call__(self, x):
		return (self.a * x + self.b) * x + self.c
	def __repr__(self):
		return f'{self.a}x^2{self.b:+}x{self.c:+}'
	def __eq__(self, o):
		return (
			type(o) == FunkcjaKwadratowa
			and self.a == o.a
			and self.b == o.b
			and self.c == o.c
		)
