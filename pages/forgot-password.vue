<!-- pages/forgot-password.vue -->
<template>
  <main class="min-h-screen flex items-center justify-center bg-slate-950 text-slate-100">
    <section class="w-full max-w-md space-y-6 p-6 rounded-xl bg-slate-900/80 border border-slate-800">
      <h1 class="text-2xl font-semibold">Reset your password</h1>
      <p class="text-sm text-slate-400">
        Enter the email address you used to sign up and we’ll send you a reset link.
      </p>
      <form class="space-y-4">
        <label class="block text-sm font-medium">
          Email
          <input
              type="email"
              class="mt-1 w-full rounded-lg border border-slate-700 bg-slate-950 px-3 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-indigo-500"
              placeholder="you@example.com"
          />
        </label>
        <button
            type="submit"
            class="w-full rounded-lg bg-indigo-500 py-2.5 text-sm font-medium hover:bg-indigo-400 transition"
        >
          Send reset link
        </button>
      </form>
      <p class="text-xs text-slate-500">
        This is a demo screen for the portfolio. The form does not send real emails.
      </p>
    </section>
  </main>
</template>